# BipNotifyApplicationStateChange

- ea: `0x18005650c`
- end: `0x1800566b8`
- name: `BipNotifyApplicationStateChange`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044b34`

## callees

- `0x18002a410`
- `0x18002b060`
- `0x18003a024`
- `0x18004aa3c`
- `0x18005650c`
- `0x180094662`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180056688`
- `ntdll!RtlFreeHeap` at `0x180056688`
- `ntdll!RtlAllocateHeap` at `0x1800565a8`
- `ntdll!RtlAllocateHeap` at `0x1800565a8`
- `ntdll!RtlCopySid` at `0x1800565d7`
- `ntdll!RtlCopySid` at `0x1800565d7`
- `ntdll!RtlLengthSid` at `0x18005658b`
- `ntdll!RtlLengthSid` at `0x18005658b`

## pseudocode

```c
__int64 __fastcall BipNotifyApplicationStateChange(int a1, unsigned __int8 *a2, __int64 a3)
{
  int v5; // ecx
  int v6; // ecx
  unsigned int v8; // ebx
  void *v9; // rax
  unsigned int v10; // r12d
  ULONG v11; // eax
  ULONG v12; // r13d
  __int64 v13; // r14
  char *Heap; // rax
  char *v15; // rdi
  unsigned int v16; // r14d
  int v17; // ecx
  __int64 v18; // r9
  __int64 v19; // r8
  unsigned int v20; // [rsp+30h] [rbp-59h] BYREF
  void *Src; // [rsp+38h] [rbp-51h] BYREF
  char v22[32]; // [rsp+40h] [rbp-49h] BYREF
  unsigned int *v23; // [rsp+60h] [rbp-29h]
  __int64 v24; // [rsp+68h] [rbp-21h]
  unsigned __int8 *v25; // [rsp+70h] [rbp-19h]
  int v26; // [rsp+78h] [rbp-11h]
  int v27; // [rsp+7Ch] [rbp-Dh]
  char v28[16]; // [rsp+80h] [rbp-9h] BYREF
  void **p_Src; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]

  v20 = 0;
  if ( a1 && (v5 = a1 - 1) != 0 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 0;
      v8 = 4;
    }
    else
    {
      v8 = 6;
    }
  }
  else
  {
    v8 = 5;
  }
  v9 = (void *)BipPackageIdToFullNameWithSize(a3, &v20);
  v10 = v20 + 2;
  Src = v9;
  v11 = RtlLengthSid(a2);
  v12 = v11 + v10 + 8;
  v13 = v11;
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, v12);
  v15 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *(_DWORD *)Heap = 8;
  *((_DWORD *)Heap + 1) = v13 + 8;
  RtlCopySid(v13, Heap + 8, a2);
  memcpy_0(&v15[v13 + 8], Src, v10);
  v16 = BipNotifyAllSubscribers(v8, v15, v12);
  if ( (unsigned int)dword_1800C3098 > 4 )
  {
    v17 = a2[1];
    v20 = v8;
    v23 = &v20;
    v24 = 4;
    v25 = a2;
    v26 = 4 * v17 + 8;
    v27 = 0;
    tlgCreate1Sz_wchar_t(v28, a3);
    v30 = v18;
    p_Src = &Src;
    LODWORD(Src) = v16;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &unk_1800AF2D8, v19, 0, 6, v22);
  }
  RtlFreeHeap(BipHeap, 0, v15);
  return v16;
}

```

## disassembly

```asm
0x18005650c  mov     [rsp-8+arg_0], rbx
0x180056511  push    rbp
0x180056512  push    rsi
0x180056513  push    rdi
0x180056514  push    r12
0x180056516  push    r13
0x180056518  push    r14
0x18005651a  push    r15
0x18005651c  lea     rbp, [rsp-27h]
0x180056521  sub     rsp, 0B0h
0x180056528  mov     rax, cs:__security_cookie
0x18005652f  xor     rax, rsp
0x180056532  mov     [rbp+57h+var_40], rax
0x180056536  mov     [rbp+57h+var_B0], 0
0x18005653d  mov     r15, r8
0x180056540  mov     rsi, rdx
0x180056543  test    ecx, ecx
0x180056545  jz      short loc_18005656B
0x180056547  sub     ecx, 1
0x18005654a  jz      short loc_18005656B
0x18005654c  sub     ecx, 1
0x18005654f  jz      short loc_180056564
0x180056551  cmp     ecx, 1
0x180056554  jz      short loc_18005655D
0x180056556  xor     eax, eax
0x180056558  jmp     loc_180056691
0x18005655d  mov     ebx, 4
0x180056562  jmp     short loc_180056570
0x180056564  mov     ebx, 6
0x180056569  jmp     short loc_180056570
0x18005656b  mov     ebx, 5
0x180056570  lea     rdx, [rbp+57h+var_B0]
0x180056574  mov     rcx, r15
0x180056577  call    BipPackageIdToFullNameWithSize
0x18005657c  mov     r12d, [rbp+57h+var_B0]
0x180056580  mov     rcx, rsi; Sid
0x180056583  add     r12d, 2
0x180056587  mov     [rbp+57h+Src], rax
0x18005658b  call    cs:__imp_RtlLengthSid
0x180056591  mov     rcx, cs:BipHeap; HeapHandle
0x180056598  lea     r13d, [r12+8]
0x18005659d  add     r13d, eax
0x1800565a0  mov     r14d, eax
0x1800565a3  mov     r8d, r13d; Size
0x1800565a6  xor     edx, edx; Flags
0x1800565a8  call    cs:__imp_RtlAllocateHeap
0x1800565ae  mov     rdi, rax
0x1800565b1  test    rax, rax
0x1800565b4  jnz     short loc_1800565C0
0x1800565b6  mov     eax, 0C0000017h
0x1800565bb  jmp     loc_180056691
0x1800565c0  mov     dword ptr [rax], 8
0x1800565c6  lea     rdx, [rdi+8]; DestinationSid
0x1800565ca  lea     eax, [r14+8]
0x1800565ce  mov     r8, rsi; SourceSid
0x1800565d1  mov     ecx, r14d; DestinationSidLength
0x1800565d4  mov     [rdi+4], eax
0x1800565d7  call    cs:__imp_RtlCopySid
0x1800565dd  mov     rdx, [rbp+57h+Src]; Src
0x1800565e1  lea     rcx, [r14+8]
0x1800565e5  add     rcx, rdi; void *
0x1800565e8  mov     r8d, r12d; Size
0x1800565eb  call    memcpy_0
0x1800565f0  mov     r8d, r13d
0x1800565f3  mov     rdx, rdi
0x1800565f6  mov     ecx, ebx
0x1800565f8  call    BipNotifyAllSubscribers
0x1800565fd  mov     ecx, cs:dword_1800C3098
0x180056603  mov     r9d, 4
0x180056609  mov     r14d, eax
0x18005660c  cmp     ecx, r9d
0x18005660f  jbe     short loc_18005667C
0x180056611  movzx   ecx, byte ptr [rsi+1]
0x180056615  lea     rax, [rbp+57h+var_B0]
0x180056619  xor     r8d, r8d
0x18005661c  mov     [rbp+57h+var_B0], ebx
0x18005661f  mov     rdx, r15
0x180056622  mov     [rbp+57h+var_80], rax
0x180056626  mov     [rbp+57h+var_78], r9
0x18005662a  lea     ecx, ds:8[rcx*4]
0x180056631  mov     [rbp+57h+var_70], rsi
0x180056635  mov     [rbp+57h+var_68], ecx
0x180056638  lea     rcx, [rbp+57h+var_60]
0x18005663c  mov     [rbp+57h+var_64], r8d
0x180056640  call    _tlgCreate1Sz_wchar_t
0x180056645  lea     rax, [rbp+57h+Src]
0x180056649  mov     [rbp+57h+var_48], r9
0x18005664d  mov     [rbp+57h+var_50], rax
0x180056651  lea     rdx, unk_1800AF2D8
0x180056658  lea     rax, [rbp+57h+var_A0]
0x18005665c  mov     dword ptr [rbp+57h+Src], r14d
0x180056660  mov     [rsp+0E0h+var_B8], rax
0x180056665  lea     rcx, dword_1800C3098
0x18005666c  xor     r9d, r9d
0x18005666f  mov     [rsp+0E0h+var_C0], 6
0x180056677  call    _tlgWriteTransfer_EventWriteTransfer
0x18005667c  mov     rcx, cs:BipHeap; HeapHandle
0x180056683  mov     r8, rdi; P
0x180056686  xor     edx, edx; Flags
0x180056688  call    cs:__imp_RtlFreeHeap
0x18005668e  mov     eax, r14d
0x180056691  mov     rcx, [rbp+57h+var_40]
0x180056695  xor     rcx, rsp; StackCookie
0x180056698  call    __security_check_cookie
0x18005669d  mov     rbx, [rsp+0E0h+arg_0]
0x1800566a5  add     rsp, 0B0h
0x1800566ac  pop     r15
0x1800566ae  pop     r14
0x1800566b0  pop     r13
0x1800566b2  pop     r12
0x1800566b4  pop     rdi
0x1800566b5  pop     rsi
0x1800566b6  pop     rbp
0x1800566b7  retn
```
