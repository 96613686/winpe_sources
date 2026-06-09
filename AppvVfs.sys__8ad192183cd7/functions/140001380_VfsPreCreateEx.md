# VfsPreCreateEx

- ea: `0x140001380`
- end: `0x140001527`
- name: `VfsPreCreateEx`
- size: `423`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001090`
- `0x140001380`
- `0x140003c00`
- `0x14000f124`
- `0x140013b00`
- `0x140013be0`
- `0x140014000`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000142d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000142d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000143c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000143c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400013bf`
- `ntoskrnl!EtwActivityIdControl` at `0x1400013bf`
- `AppvVemgr!VeMgrLookupProcess` at `0x140001456`
- `AppvVemgr!VeMgrLookupProcess` at `0x140001456`

## pseudocode

```c
__int64 __fastcall VfsPreCreateEx(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  HANDLE CurrentThreadId; // rbx
  HANDLE CurrentProcessId; // rax
  int v10; // eax
  unsigned int v11; // ebx
  GUID Buf2[2]; // [rsp+30h] [rbp-79h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-59h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-49h] BYREF
  __int128 v16; // [rsp+70h] [rbp-39h]
  _BYTE v17[80]; // [rsp+80h] [rbp-29h] BYREF

  ActivityId = GUID_NULL;
  if ( EtwActivityIdControl(1u, &ActivityId) < 0 )
    ActivityId = GUID_NULL;
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v6, VFSC_PreCreateStart, &ActivityId);
  Buf1 = 0;
  v16 = 0;
  memset(v17, 0, 0x44u);
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 6LL) & 2) == 0 && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) == 0 )
  {
    CurrentThreadId = PsGetCurrentThreadId();
    CurrentProcessId = PsGetCurrentProcessId();
    v10 = VeMgrLookupProcess(CurrentProcessId, CurrentThreadId, &Buf1, v17);
    if ( v10 < 0 )
    {
      if ( v10 != -1073741772 )
      {
        *(_DWORD *)(a1 + 24) = v10;
        goto LABEL_15;
      }
      Buf1 = 0;
      v16 = 0;
    }
    memset(Buf2, 0, sizeof(Buf2));
    if ( memcmp(&Buf1, Buf2, 0x20u) )
    {
      v11 = VfsCreateCommon(&Buf1, v17, a1, a2, a3);
      goto LABEL_18;
    }
    v7 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 64LL);
    if ( v7 && (unsigned __int8)VfsDecodeFileObject(v7, 0, 0) )
    {
      *(_DWORD *)(a1 + 24) = -1073741790;
LABEL_15:
      *(_QWORD *)(a1 + 32) = 0;
      v11 = 4;
      goto LABEL_18;
    }
  }
  v11 = 1;
LABEL_18:
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v7, VFSC_PreCreateFinish, &ActivityId);
  return v11;
}

```

## disassembly

```asm
0x140001380  push    rbp
0x140001382  push    rbx
0x140001383  push    rsi
0x140001384  push    rdi
0x140001385  push    r14
0x140001387  lea     rbp, [rsp-37h]
0x14000138c  sub     rsp, 0E0h
0x140001393  mov     rax, cs:__security_cookie
0x14000139a  xor     rax, rsp
0x14000139d  mov     [rbp+57h+var_30], rax
0x1400013a1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400013a8  mov     rsi, rdx
0x1400013ab  mov     rdi, rcx
0x1400013ae  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400013b2  mov     ecx, 1; ControlCode
0x1400013b7  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1400013bc  mov     r14, r8
0x1400013bf  call    cs:__imp_EtwActivityIdControl
0x1400013c6  nop     dword ptr [rax+rax+00h]
0x1400013cb  test    eax, eax
0x1400013cd  jns     short loc_1400013DB
0x1400013cf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400013d6  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1400013db  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400013e2  jz      short loc_1400013F4
0x1400013e4  lea     r8, [rbp+57h+ActivityId]
0x1400013e8  lea     rdx, VFSC_PreCreateStart
0x1400013ef  call    McTemplateK0_EtwWriteTransfer
0x1400013f4  xorps   xmm0, xmm0
0x1400013f7  lea     rcx, [rbp+57h+var_80]; void *
0x1400013fb  xor     edx, edx; Val
0x1400013fd  movups  [rbp+57h+Buf1], xmm0
0x140001401  movups  [rbp+57h+var_90], xmm0
0x140001405  lea     r8d, [rdx+44h]; Size
0x140001409  call    memset
0x14000140e  mov     rax, [rdi+10h]
0x140001412  test    byte ptr [rax+6], 2
0x140001416  jnz     loc_1400014EC
0x14000141c  mov     rax, [rsi+20h]
0x140001420  test    dword ptr [rax+50h], 400000h
0x140001427  jnz     loc_1400014EC
0x14000142d  call    cs:__imp_PsGetCurrentThreadId
0x140001434  nop     dword ptr [rax+rax+00h]
0x140001439  mov     rbx, rax
0x14000143c  call    cs:__imp_PsGetCurrentProcessId
0x140001443  nop     dword ptr [rax+rax+00h]
0x140001448  lea     r9, [rbp+57h+var_80]
0x14000144c  mov     rdx, rbx
0x14000144f  mov     rcx, rax
0x140001452  lea     r8, [rbp+57h+Buf1]
0x140001456  call    cs:__imp_VeMgrLookupProcess
0x14000145d  nop     dword ptr [rax+rax+00h]
0x140001462  test    eax, eax
0x140001464  jns     short loc_140001478
0x140001466  cmp     eax, 0C0000034h
0x14000146b  jnz     short loc_1400014BE
0x14000146d  xorps   xmm0, xmm0
0x140001470  movups  [rbp+57h+Buf1], xmm0
0x140001474  movups  [rbp+57h+var_90], xmm0
0x140001478  xorps   xmm0, xmm0
0x14000147b  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14000147f  mov     r8d, 20h ; ' '; Size
0x140001485  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140001489  movups  [rbp+57h+Buf2], xmm0
0x14000148d  movups  [rbp+57h+var_C0], xmm0
0x140001491  call    memcmp
0x140001496  test    eax, eax
0x140001498  jnz     short loc_1400014D0
0x14000149a  mov     rax, [rsi+20h]
0x14000149e  mov     rcx, [rax+40h]
0x1400014a2  test    rcx, rcx
0x1400014a5  jz      short loc_1400014EC
0x1400014a7  xor     r8d, r8d
0x1400014aa  xor     edx, edx
0x1400014ac  call    VfsDecodeFileObject
0x1400014b1  test    al, al
0x1400014b3  jz      short loc_1400014EC
0x1400014b5  mov     dword ptr [rdi+18h], 0C0000022h
0x1400014bc  jmp     short loc_1400014C1
0x1400014be  mov     [rdi+18h], eax
0x1400014c1  mov     qword ptr [rdi+20h], 0
0x1400014c9  mov     ebx, 4
0x1400014ce  jmp     short loc_1400014F1
0x1400014d0  mov     r9, rsi
0x1400014d3  mov     [rsp+100h+var_E0], r14
0x1400014d8  mov     r8, rdi
0x1400014db  lea     rdx, [rbp+57h+var_80]
0x1400014df  lea     rcx, [rbp+57h+Buf1]
0x1400014e3  call    VfsCreateCommon
0x1400014e8  mov     ebx, eax
0x1400014ea  jmp     short loc_1400014F1
0x1400014ec  mov     ebx, 1
0x1400014f1  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400014f8  jz      short loc_14000150A
0x1400014fa  lea     r8, [rbp+57h+ActivityId]
0x1400014fe  lea     rdx, VFSC_PreCreateFinish
0x140001505  call    McTemplateK0_EtwWriteTransfer
0x14000150a  mov     eax, ebx
0x14000150c  mov     rcx, [rbp+57h+var_30]
0x140001510  xor     rcx, rsp; StackCookie
0x140001513  call    __security_check_cookie
0x140001518  add     rsp, 0E0h
0x14000151f  pop     r14
0x140001521  pop     rdi
0x140001522  pop     rsi
0x140001523  pop     rbx
0x140001524  pop     rbp
0x140001525  retn
```
