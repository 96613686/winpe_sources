# BipEnumerateWorkItems

- ea: `0x180016e14`
- end: `0x180017017`
- name: `BipEnumerateWorkItems`
- size: `515`
- prototype: `__int64 __usercall@<rax>(PSID Sid2@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180016270`

## callees

- `0x180016e14`
- `0x18002b060`
- `0x1800339b0`
- `0x180043538`
- `0x180048248`
- `0x180053100`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180016f07`
- `ntdll!RtlReAllocateHeap` at `0x180016f07`
- `ntdll!RtlFreeHeap` at `0x180016f63`
- `ntdll!RtlFreeHeap` at `0x180016f63`
- `ntdll!RtlAllocateHeap` at `0x180016e8a`
- `ntdll!RtlAllocateHeap` at `0x180016e8a`
- `ntdll!RtlEqualSid` at `0x180016ec5`
- `ntdll!RtlEqualSid` at `0x180016ee2`
- `ntdll!RtlEqualSid` at `0x180016ec5`
- `ntdll!RtlEqualSid` at `0x180016ee2`

## pseudocode

```c
__int64 __fastcall BipEnumerateWorkItems(PSID Sid2, __int64 a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  _QWORD *v5; // r15
  __int64 v8; // rdi
  int v9; // ebx
  __int64 v10; // r8
  int v11; // esi
  PVOID Heap; // r14
  unsigned int v13; // r15d
  void *v14; // rcx
  void *v15; // rcx
  PVOID v16; // rax
  __int64 v17; // rax
  __int64 v18; // rsi
  int v20; // [rsp+30h] [rbp-81h] BYREF
  int v21; // [rsp+34h] [rbp-7Dh] BYREF
  __int64 v22; // [rsp+38h] [rbp-79h] BYREF
  _OWORD v23[3]; // [rsp+40h] [rbp-71h] BYREF
  char v24[32]; // [rsp+70h] [rbp-41h] BYREF
  int *v25; // [rsp+90h] [rbp-21h]
  __int64 v26; // [rsp+98h] [rbp-19h]
  int *v27; // [rsp+A0h] [rbp-11h]
  __int64 v28; // [rsp+A8h] [rbp-9h]
  __int64 *v29; // [rsp+B0h] [rbp-1h]
  __int64 v30; // [rsp+B8h] [rbp+7h]

  v5 = a5;
  v22 = (__int64)a5;
  v8 = 0;
  memset(v23, 0, sizeof(v23));
  v9 = BipTableEnumerationBegin(&qword_1800C4388, v23);
  if ( v9 >= 0 )
  {
    Heap = RtlAllocateHeap(BipHeap, 0, 0x200u);
    if ( Heap )
    {
      v13 = 64;
      while ( 1 )
      {
        v17 = BipTableEnumerationNext(v23);
        v18 = v17;
        if ( !v17 )
          break;
        if ( Sid2 )
        {
          v14 = *(void **)(*(_QWORD *)(v17 + 72) + 168LL);
          if ( !v14 )
            continue;
          if ( !RtlEqualSid(v14, Sid2) )
          {
            v15 = *(void **)(*(_QWORD *)(v18 + 72) + 176LL);
            if ( !v15 || !RtlEqualSid(v15, Sid2) )
              continue;
          }
        }
        if ( (unsigned int)v8 >= v13 )
        {
          v13 *= 2;
          v16 = RtlReAllocateHeap(BipHeap, 0, Heap, 8LL * v13);
          if ( !v16 )
          {
            v9 = -1073741801;
            break;
          }
          Heap = v16;
        }
        *((_QWORD *)Heap + v8) = v18;
        v8 = (unsigned int)(v8 + 1);
      }
      v5 = (_QWORD *)v22;
      v11 = 0;
    }
    else
    {
      v9 = -1073741801;
      v11 = 20;
    }
    BipTableEnumerationEnd(v23);
    if ( v9 >= 0 )
    {
      *a4 = v8;
      *v5 = Heap;
      return (unsigned int)v9;
    }
    if ( Heap )
      RtlFreeHeap(BipHeap, 0, Heap);
  }
  else
  {
    v11 = 10;
  }
  if ( (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v10) )
  {
    v20 = v8;
    v25 = &v20;
    v26 = 4;
    v27 = &v21;
    v21 = v9;
    v29 = &v22;
    v28 = 4;
    LODWORD(v22) = v11;
    v30 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, byte_1800B1363, 0, 0, 5, v24);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016e14  mov     [rsp-8+arg_8], rbx
0x180016e19  push    rbp
0x180016e1a  push    rsi
0x180016e1b  push    rdi
0x180016e1c  push    r12
0x180016e1e  push    r13
0x180016e20  push    r14
0x180016e22  push    r15
0x180016e24  lea     rbp, [rsp-1Fh]
0x180016e29  sub     rsp, 0D0h
0x180016e30  mov     rax, cs:__security_cookie
0x180016e37  xor     rax, rsp
0x180016e3a  mov     [rbp+4Fh+var_40], rax
0x180016e3e  mov     r15, [rbp+4Fh+arg_20]
0x180016e42  lea     rdx, [rbp+4Fh+var_C0]
0x180016e46  xorps   xmm0, xmm0
0x180016e49  mov     [rbp+4Fh+var_C8], r15
0x180016e4d  mov     r12, rcx
0x180016e50  mov     r13, r9
0x180016e53  lea     rcx, qword_1800C4388
0x180016e5a  xor     edi, edi
0x180016e5c  movups  [rbp+4Fh+var_C0], xmm0
0x180016e60  movups  [rbp+4Fh+var_B0], xmm0
0x180016e64  movups  [rbp+4Fh+var_A0], xmm0
0x180016e68  call    BipTableEnumerationBegin
0x180016e6d  mov     ebx, eax
0x180016e6f  test    eax, eax
0x180016e71  jns     short loc_180016E7B
0x180016e73  lea     esi, [rdi+0Ah]
0x180016e76  jmp     loc_180016F69
0x180016e7b  mov     rcx, cs:BipHeap; HeapHandle
0x180016e82  xor     edx, edx; Flags
0x180016e84  mov     r8d, 200h; Size
0x180016e8a  call    cs:__imp_RtlAllocateHeap
0x180016e90  mov     r14, rax
0x180016e93  test    rax, rax
0x180016e96  jnz     short loc_180016EA5
0x180016e98  mov     ebx, 0C0000017h
0x180016e9d  lea     esi, [rax+14h]
0x180016ea0  jmp     loc_180016F39
0x180016ea5  mov     r15d, 40h ; '@'
0x180016eab  jmp     short loc_180016F1B
0x180016ead  test    r12, r12
0x180016eb0  jz      short loc_180016EEC
0x180016eb2  mov     rcx, [rsi+48h]
0x180016eb6  mov     rcx, [rcx+0A8h]; Sid1
0x180016ebd  test    rcx, rcx
0x180016ec0  jz      short loc_180016F1B
0x180016ec2  mov     rdx, r12; Sid2
0x180016ec5  call    cs:__imp_RtlEqualSid
0x180016ecb  test    al, al
0x180016ecd  jnz     short loc_180016EEC
0x180016ecf  mov     rax, [rsi+48h]
0x180016ed3  mov     rcx, [rax+0B0h]; Sid1
0x180016eda  test    rcx, rcx
0x180016edd  jz      short loc_180016F1B
0x180016edf  mov     rdx, r12; Sid2
0x180016ee2  call    cs:__imp_RtlEqualSid
0x180016ee8  test    al, al
0x180016eea  jz      short loc_180016F1B
0x180016eec  cmp     edi, r15d
0x180016eef  jb      short loc_180016F15
0x180016ef1  mov     rcx, cs:BipHeap; Heap
0x180016ef8  add     r15d, r15d
0x180016efb  mov     r9d, r15d
0x180016efe  mov     r8, r14; Ptr
0x180016f01  shl     r9, 3; Size
0x180016f05  xor     edx, edx; Flags
0x180016f07  call    cs:__imp_RtlReAllocateHeap
0x180016f0d  test    rax, rax
0x180016f10  jz      short loc_180016F2E
0x180016f12  mov     r14, rax
0x180016f15  mov     [r14+rdi*8], rsi
0x180016f19  inc     edi
0x180016f1b  lea     rcx, [rbp+4Fh+var_C0]
0x180016f1f  call    BipTableEnumerationNext
0x180016f24  mov     rsi, rax
0x180016f27  test    rax, rax
0x180016f2a  jnz     short loc_180016EAD
0x180016f2c  jmp     short loc_180016F33
0x180016f2e  mov     ebx, 0C0000017h
0x180016f33  mov     r15, [rbp+4Fh+var_C8]
0x180016f37  xor     esi, esi
0x180016f39  lea     rcx, [rbp+4Fh+var_C0]
0x180016f3d  call    BipTableEnumerationEnd
0x180016f42  test    ebx, ebx
0x180016f44  js      short loc_180016F52
0x180016f46  mov     [r13+0], edi
0x180016f4a  mov     [r15], r14
0x180016f4d  jmp     loc_180016FEE
0x180016f52  test    r14, r14
0x180016f55  jz      short loc_180016F69
0x180016f57  mov     rcx, cs:BipHeap; HeapHandle
0x180016f5e  mov     r8, r14; P
0x180016f61  xor     edx, edx; Flags
0x180016f63  call    cs:__imp_RtlFreeHeap
0x180016f69  mov     eax, cs:dword_1800C3098
0x180016f6f  cmp     eax, 2
0x180016f72  jbe     short loc_180016FEE
0x180016f74  mov     edx, 3
0x180016f79  lea     rcx, dword_1800C3098
0x180016f80  call    _tlgKeywordOn
0x180016f85  test    al, al
0x180016f87  jz      short loc_180016FEE
0x180016f89  lea     rax, [rsp+100h+var_D0]
0x180016f8e  mov     [rsp+100h+var_D0], edi
0x180016f92  mov     [rbp+4Fh+var_70], rax
0x180016f96  lea     rdx, byte_1800B1363
0x180016f9d  lea     rax, [rbp+4Fh+var_CC]
0x180016fa1  mov     [rbp+4Fh+var_68], 4
0x180016fa9  mov     [rbp+4Fh+var_60], rax
0x180016fad  lea     rcx, dword_1800C3098
0x180016fb4  lea     rax, [rbp+4Fh+var_C8]
0x180016fb8  mov     [rbp+4Fh+var_CC], ebx
0x180016fbb  mov     [rbp+4Fh+var_50], rax
0x180016fbf  xor     r9d, r9d
0x180016fc2  lea     rax, [rbp+4Fh+var_90]
0x180016fc6  mov     [rbp+4Fh+var_58], 4
0x180016fce  mov     [rsp+100h+var_D8], rax
0x180016fd3  xor     r8d, r8d
0x180016fd6  mov     [rsp+100h+var_E0], 5
0x180016fde  mov     dword ptr [rbp+4Fh+var_C8], esi
0x180016fe1  mov     [rbp+4Fh+var_48], 4
0x180016fe9  call    _tlgWriteTransfer_EventWriteTransfer
0x180016fee  mov     eax, ebx
0x180016ff0  mov     rcx, [rbp+4Fh+var_40]
0x180016ff4  xor     rcx, rsp; StackCookie
0x180016ff7  call    __security_check_cookie
0x180016ffc  mov     rbx, [rsp+100h+arg_8]
0x180017004  add     rsp, 0D0h
0x18001700b  pop     r15
0x18001700d  pop     r14
0x18001700f  pop     r13
0x180017011  pop     r12
0x180017013  pop     rdi
0x180017014  pop     rsi
0x180017015  pop     rbp
0x180017016  retn
```
