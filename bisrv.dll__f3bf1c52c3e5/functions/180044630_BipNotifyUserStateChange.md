# BipNotifyUserStateChange

- ea: `0x180044630`
- end: `0x1800447ce`
- name: `BipNotifyUserStateChange`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044510`
- `0x1800445d4`

## callees

- `0x18002b060`
- `0x18003a024`
- `0x180044630`
- `0x180053100`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800446cf`
- `ntdll!RtlFreeHeap` at `0x1800446cf`
- `ntdll!RtlAllocateHeap` at `0x180044681`
- `ntdll!RtlAllocateHeap` at `0x180044681`
- `ntdll!RtlCopySid` at `0x1800446ad`
- `ntdll!RtlCopySid` at `0x1800446ad`
- `ntdll!RtlLengthSid` at `0x180044669`
- `ntdll!RtlLengthSid` at `0x180044669`

## pseudocode

```c
__int64 __fastcall BipNotifyUserStateChange(unsigned int a1, int a2, __int64 a3, void *a4)
{
  ULONG v8; // ebx
  char *Heap; // rax
  void *v10; // rdi
  unsigned int v11; // edi
  int v12; // ebx
  int v13; // r8d
  __int64 *v14; // rax
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-79h] BYREF
  int v18; // [rsp+34h] [rbp-75h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-71h] BYREF
  __int64 v20; // [rsp+40h] [rbp-69h] BYREF
  char v21[32]; // [rsp+50h] [rbp-59h] BYREF
  int *v22; // [rsp+70h] [rbp-39h]
  __int64 v23; // [rsp+78h] [rbp-31h]
  int *v24; // [rsp+80h] [rbp-29h]
  __int64 v25; // [rsp+88h] [rbp-21h]
  __int64 *v26; // [rsp+90h] [rbp-19h]
  int v27; // [rsp+98h] [rbp-11h]
  int v28; // [rsp+9Ch] [rbp-Dh]
  __int64 *v29; // [rsp+A0h] [rbp-9h]
  __int64 v30; // [rsp+A8h] [rbp-1h]
  unsigned int *v31; // [rsp+B0h] [rbp+7h]
  __int64 v32; // [rsp+B8h] [rbp+Fh]

  v8 = RtlLengthSid(a4);
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, v8 + 20);
  v10 = Heap;
  if ( Heap )
  {
    *((_DWORD *)Heap + 4) = 0;
    *(_DWORD *)Heap = a2;
    *((_QWORD *)Heap + 1) = a3;
    RtlCopySid(v8, Heap + 20, a4);
    v12 = BipNotifyAllSubscribers(a1, v10, v8 + 20);
    RtlFreeHeap(BipHeap, 0, v10);
    v11 = 0;
    if ( v12 < 0 )
      v11 = v12;
  }
  else
  {
    v11 = -1073741801;
  }
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, 0) )
  {
    v28 = v13;
    v22 = (int *)&v17;
    v17 = a1;
    v24 = &v18;
    v23 = 4;
    v14 = &BipTraceLoggingNullSid;
    v18 = a2;
    if ( a4 )
      v14 = (__int64 *)a4;
    v25 = 4;
    v26 = v14;
    v20 = a3;
    v30 = 8;
    v15 = *((unsigned __int8 *)v14 + 1);
    v19 = v11;
    v32 = 4;
    v27 = 4 * v15 + 8;
    v29 = &v20;
    v31 = &v19;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &dword_1800AF124, 0, 0, 7, v21);
  }
  return v11;
}

```

## disassembly

```asm
0x180044630  mov     [rsp-8+arg_8], rbx
0x180044635  push    rbp
0x180044636  push    rsi
0x180044637  push    rdi
0x180044638  push    r12
0x18004463a  push    r13
0x18004463c  push    r14
0x18004463e  push    r15
0x180044640  lea     rbp, [rsp-27h]
0x180044645  sub     rsp, 0D0h
0x18004464c  mov     rax, cs:__security_cookie
0x180044653  xor     rax, rsp
0x180044656  mov     [rbp+57h+var_40], rax
0x18004465a  mov     r13d, ecx
0x18004465d  mov     rsi, r9
0x180044660  mov     rcx, r9; Sid
0x180044663  mov     r15, r8
0x180044666  mov     r12d, edx
0x180044669  call    cs:__imp_RtlLengthSid
0x18004466f  mov     rcx, cs:BipHeap; HeapHandle
0x180044676  xor     edx, edx; Flags
0x180044678  mov     ebx, eax
0x18004467a  lea     r14d, [rax+14h]
0x18004467e  mov     r8d, r14d; Size
0x180044681  call    cs:__imp_RtlAllocateHeap
0x180044687  xor     r8d, r8d
0x18004468a  mov     rdi, rax
0x18004468d  test    rax, rax
0x180044690  jnz     short loc_180044699
0x180044692  mov     edi, 0C0000017h
0x180044697  jmp     short loc_1800446E0
0x180044699  mov     [rax+10h], r8d
0x18004469d  lea     rdx, [rax+14h]; DestinationSid
0x1800446a1  mov     r8, rsi; SourceSid
0x1800446a4  mov     [rax], r12d
0x1800446a7  mov     ecx, ebx; DestinationSidLength
0x1800446a9  mov     [rax+8], r15
0x1800446ad  call    cs:__imp_RtlCopySid
0x1800446b3  mov     r8d, r14d
0x1800446b6  mov     rdx, rdi
0x1800446b9  mov     ecx, r13d
0x1800446bc  call    BipNotifyAllSubscribers
0x1800446c1  mov     ebx, eax
0x1800446c3  mov     rcx, cs:BipHeap; HeapHandle
0x1800446ca  mov     r8, rdi; P
0x1800446cd  xor     edx, edx; Flags
0x1800446cf  call    cs:__imp_RtlFreeHeap
0x1800446d5  xor     r8d, r8d
0x1800446d8  test    ebx, ebx
0x1800446da  mov     edi, r8d
0x1800446dd  cmovs   edi, ebx
0x1800446e0  mov     eax, cs:dword_1800C3098
0x1800446e6  cmp     eax, 5
0x1800446e9  jbe     loc_1800447A5
0x1800446ef  mov     edx, 2
0x1800446f4  lea     rcx, dword_1800C3098
0x1800446fb  call    _tlgKeywordOn
0x180044700  test    al, al
0x180044702  jz      loc_1800447A5
0x180044708  lea     rax, [rbp+57h+var_D0]
0x18004470c  mov     [rbp+57h+var_64], r8d
0x180044710  mov     [rbp+57h+var_90], rax
0x180044714  lea     rdx, dword_1800AF124
0x18004471b  lea     rax, [rbp+57h+var_CC]
0x18004471f  mov     [rbp+57h+var_D0], r13d
0x180044723  mov     [rbp+57h+var_80], rax
0x180044727  lea     rcx, dword_1800C3098
0x18004472e  test    rsi, rsi
0x180044731  mov     [rbp+57h+var_88], 4
0x180044739  lea     rax, BipTraceLoggingNullSid
0x180044740  mov     [rbp+57h+var_CC], r12d
0x180044744  cmovnz  rax, rsi
0x180044748  mov     [rbp+57h+var_78], 4
0x180044750  mov     [rbp+57h+var_70], rax
0x180044754  xor     r9d, r9d
0x180044757  xor     r8d, r8d
0x18004475a  mov     [rbp+57h+var_C0], r15
0x18004475e  mov     [rbp+57h+var_58], 8
0x180044766  movzx   eax, byte ptr [rax+1]
0x18004476a  mov     [rbp+57h+var_C8], edi
0x18004476d  mov     [rbp+57h+var_48], 4
0x180044775  lea     eax, ds:8[rax*4]
0x18004477c  mov     [rbp+57h+var_68], eax
0x18004477f  lea     rax, [rbp+57h+var_C0]
0x180044783  mov     [rbp+57h+var_60], rax
0x180044787  lea     rax, [rbp+57h+var_C8]
0x18004478b  mov     [rbp+57h+var_50], rax
0x18004478f  lea     rax, [rbp+57h+var_B0]
0x180044793  mov     [rsp+100h+var_D8], rax
0x180044798  mov     [rsp+100h+var_E0], 7
0x1800447a0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800447a5  mov     eax, edi
0x1800447a7  mov     rcx, [rbp+57h+var_40]
0x1800447ab  xor     rcx, rsp; StackCookie
0x1800447ae  call    __security_check_cookie
0x1800447b3  mov     rbx, [rsp+100h+arg_8]
0x1800447bb  add     rsp, 0D0h
0x1800447c2  pop     r15
0x1800447c4  pop     r14
0x1800447c6  pop     r13
0x1800447c8  pop     r12
0x1800447ca  pop     rdi
0x1800447cb  pop     rsi
0x1800447cc  pop     rbp
0x1800447cd  retn
```
