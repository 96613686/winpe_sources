# AiRegReadStringValue

- ea: `0x18000879c`
- end: `0x180008904`
- name: `AiRegReadStringValue`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180004ca0`

## callees

- `0x180003fd4`
- `0x180008668`
- `0x18000879c`
- `0x180009562`

## import_xrefs

- `ntdll!NtClose` at `0x1800088ef`
- `ntdll!NtClose` at `0x1800088ef`
- `ntdll!RtlFreeHeap` at `0x1800087f4`
- `ntdll!RtlFreeHeap` at `0x1800088df`
- `ntdll!RtlFreeHeap` at `0x1800087f4`
- `ntdll!RtlFreeHeap` at `0x1800088df`
- `ntdll!NtQueryValueKey` at `0x18000882c`
- `ntdll!NtQueryValueKey` at `0x18000882c`

## pseudocode

```c
__int64 __fastcall AiRegReadStringValue(__int64 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, __int64 a4)
{
  _DWORD *v5; // rdi
  NTSTATUS v7; // ebx
  ULONG Length; // ebx
  NTSTATUS v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // edx
  __int64 v12; // rcx
  void *v13; // rax
  HANDLE KeyHandle; // [rsp+30h] [rbp-48h] BYREF
  ULONG ResultLength; // [rsp+80h] [rbp+8h] BYREF
  int v17; // [rsp+84h] [rbp+Ch]

  v17 = HIDWORD(a1);
  ResultLength = 48;
  KeyHandle = 0;
  v5 = 0;
  v7 = AiRegOpenKey(a1, a2, (__int64)a3, &KeyHandle);
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      Length = ResultLength;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      v5 = (_DWORD *)AiAlloc(Length);
      if ( !v5 )
        break;
      v9 = NtQueryValueKey(KeyHandle, a3, KeyValuePartialInformation, v5, Length, &ResultLength);
      v7 = v9;
      if ( v9 != -2147483643 )
      {
        if ( v9 < 0 )
          goto LABEL_18;
        if ( v5[1] != 1 && v5[1] != 7 || (v10 = v5[2], v10 - 2 > 0xFFFD) || (v10 & 1) != 0 )
        {
          v7 = -1073741788;
          goto LABEL_18;
        }
        v11 = v10 >> 1;
        if ( *((_WORD *)v5 + v11 + 5) || v5[1] == 7 && v11 != 1 && *((_WORD *)v5 + v11 + 4) )
        {
          v7 = -1073739509;
          goto LABEL_18;
        }
        *(_WORD *)a4 = *((_WORD *)v5 + 4) - 2;
        v12 = *((unsigned __int16 *)v5 + 4);
        *(_WORD *)(a4 + 2) = *((_WORD *)v5 + 4);
        v13 = (void *)AiAlloc(v12);
        *(_QWORD *)(a4 + 8) = v13;
        if ( v13 )
        {
          memcpy_0(v13, v5 + 3, *(unsigned __int16 *)(a4 + 2));
          goto LABEL_18;
        }
        break;
      }
    }
    v7 = -1073741801;
  }
LABEL_18:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000879c  mov     rax, rsp
0x18000879f  mov     [rax+8], rcx
0x1800087a3  push    rbx
0x1800087a4  push    rbp
0x1800087a5  push    rsi
0x1800087a6  push    rdi
0x1800087a7  push    r14
0x1800087a9  push    r15
0x1800087ab  sub     rsp, 48h
0x1800087af  mov     r14, r9
0x1800087b2  mov     dword ptr [rax+8], 30h ; '0'
0x1800087b9  xor     ebp, ebp
0x1800087bb  lea     r9, [rax-48h]
0x1800087bf  mov     [rax-48h], rbp
0x1800087c3  mov     edi, ebp
0x1800087c5  mov     rsi, r8
0x1800087c8  call    AiRegOpenKey
0x1800087cd  mov     ebx, eax
0x1800087cf  test    eax, eax
0x1800087d1  js      loc_1800088CD
0x1800087d7  lea     r15d, [rbp+2]
0x1800087db  mov     rcx, gs:60h
0x1800087e4  mov     r8, rdi; P
0x1800087e7  mov     ebx, [rsp+78h+arg_0]
0x1800087ee  xor     edx, edx; Flags
0x1800087f0  mov     rcx, [rcx+30h]; HeapHandle
0x1800087f4  call    cs:__imp_RtlFreeHeap
0x1800087fa  mov     ecx, ebx
0x1800087fc  call    AiAlloc
0x180008801  mov     rdi, rax
0x180008804  test    rax, rax
0x180008807  jz      loc_1800088C8
0x18000880d  mov     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x180008812  lea     rax, [rsp+78h+arg_0]
0x18000881a  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18000881f  mov     r9, rdi; KeyValueInformation
0x180008822  mov     r8d, r15d; KeyValueInformationClass
0x180008825  mov     [rsp+78h+Length], ebx; Length
0x180008829  mov     rdx, rsi; ValueName
0x18000882c  call    cs:__imp_NtQueryValueKey
0x180008832  mov     ebx, eax
0x180008834  cmp     eax, 80000005h
0x180008839  jz      short loc_1800087DB
0x18000883b  test    eax, eax
0x18000883d  js      loc_1800088CD
0x180008843  cmp     dword ptr [rdi+4], 1
0x180008847  jz      short loc_180008856
0x180008849  cmp     dword ptr [rdi+4], 7
0x18000884d  jz      short loc_180008856
0x18000884f  mov     ebx, 0C0000024h
0x180008854  jmp     short loc_1800088CD
0x180008856  mov     edx, [rdi+8]
0x180008859  lea     eax, [rdx-2]
0x18000885c  cmp     eax, 0FFFDh
0x180008861  ja      short loc_18000884F
0x180008863  test    dl, 1
0x180008866  jnz     short loc_18000884F
0x180008868  shr     edx, 1
0x18000886a  lea     eax, [rdx-1]
0x18000886d  cmp     [rdi+rax*2+0Ch], bp
0x180008872  jnz     short loc_1800088C1
0x180008874  cmp     dword ptr [rdi+4], 7
0x180008878  jnz     short loc_180008889
0x18000887a  cmp     edx, 1
0x18000887d  jz      short loc_180008889
0x18000887f  lea     eax, [rdx-2]
0x180008882  cmp     [rdi+rax*2+0Ch], bp
0x180008887  jnz     short loc_1800088C1
0x180008889  movzx   eax, word ptr [rdi+8]
0x18000888d  sub     ax, r15w
0x180008891  mov     [r14], ax
0x180008895  movzx   eax, word ptr [rdi+8]
0x180008899  mov     ecx, eax
0x18000889b  mov     [r14+2], ax
0x1800088a0  call    AiAlloc
0x1800088a5  mov     [r14+8], rax
0x1800088a9  test    rax, rax
0x1800088ac  jz      short loc_1800088C8
0x1800088ae  movzx   r8d, word ptr [r14+2]; Size
0x1800088b3  lea     rdx, [rdi+0Ch]; Src
0x1800088b7  mov     rcx, rax; void *
0x1800088ba  call    memcpy_0
0x1800088bf  jmp     short loc_1800088CD
0x1800088c1  mov     ebx, 0C000090Bh
0x1800088c6  jmp     short loc_1800088CD
0x1800088c8  mov     ebx, 0C0000017h
0x1800088cd  mov     rcx, gs:60h
0x1800088d6  mov     r8, rdi; P
0x1800088d9  xor     edx, edx; Flags
0x1800088db  mov     rcx, [rcx+30h]; HeapHandle
0x1800088df  call    cs:__imp_RtlFreeHeap
0x1800088e5  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x1800088ea  test    rcx, rcx
0x1800088ed  jz      short loc_1800088F5
0x1800088ef  call    cs:__imp_NtClose
0x1800088f5  mov     eax, ebx
0x1800088f7  add     rsp, 48h
0x1800088fb  pop     r15
0x1800088fd  pop     r14
0x1800088ff  pop     rdi
0x180008900  pop     rsi
0x180008901  pop     rbp
0x180008902  pop     rbx
0x180008903  retn
```
