# AppCompatUtility::UTF16StringFromASCIIString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,char const *,unsigned __int64)

- ea: `0x180044bd0`
- end: `0x180044d7d`
- name: `?UTF16StringFromASCIIString@AppCompatUtility@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_K@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001325c`

## callees

- `0x18000c190`
- `0x180044bd0`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180044c68`
- `ntdll!RtlAllocateHeap` at `0x180044c68`
- `ntdll!RtlFreeHeap` at `0x180044d38`
- `ntdll!RtlFreeHeap` at `0x180044d38`

## string_xrefs

- `0x180044c90`: `AppCompatUtility::UTF16StringFromASCIIString`
- `0x180044d58`: `AppCompatUtility::UTF16StringFromASCIIString`

## pseudocode

```c
__int64 __fastcall AppCompatUtility::UTF16StringFromASCIIString(char **a1, _BYTE *a2, unsigned __int64 a3)
{
  unsigned __int64 v5; // r9
  _BYTE *i; // rax
  unsigned int v7; // ebx
  unsigned __int64 v8; // r14
  _BYTE *Heap; // rdi
  unsigned __int64 j; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // r14
  __int64 v13; // rbx
  unsigned int v15; // [rsp+78h] [rbp+10h]

  if ( !a2 || a3 > 0x7FFFFFFF )
  {
    v7 = -2147024809;
LABEL_22:
    AslLogCallPrintf(
      1,
      "AppCompatUtility::UTF16StringFromASCIIString",
      1190,
      "Failed to get length. [0x%x]",
      -2147024809);
    return v7;
  }
  v5 = a3;
  for ( i = a2; v5; --v5 )
  {
    if ( !*i )
      break;
    ++i;
  }
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (a3 - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
    goto LABEL_22;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v8 + 2);
  if ( Heap )
  {
    v15 = v7;
    for ( j = 0; j < v8; ++j )
    {
      Heap[2 * j] = a2[j];
      Heap[2 * j + 1] = 0;
    }
    *(_WORD *)&Heap[2 * v8] = 0;
    try
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&Heap[2 * v11] );
      if ( v11 > (unsigned __int64)a1[3] )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1);
      }
      else
      {
        if ( (unsigned __int64)a1[3] <= 7 )
          v12 = (char *)a1;
        else
          v12 = *a1;
        a1[2] = (char *)v11;
        v13 = 2 * v11;
        memmove_0(v12, Heap, 2 * v11);
        *(_WORD *)&v12[v13] = 0;
      }
    }
    catch ( ... )
    {
      AslLogCallPrintf(1, "AppCompatUtility::UTF16StringFromASCIIString", 1218, "Failed to create std::wstring.");
      v7 = v15;
      goto LABEL_20;
    }
    v7 = 0;
LABEL_20:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  else
  {
    v7 = -2147024882;
    AslLogCallPrintf(
      1,
      "AppCompatUtility::UTF16StringFromASCIIString",
      1198,
      "Failed to allocate memory for StringBuffer.");
  }
  return v7;
}

```

## disassembly

```asm
0x180044bd0  push    rsi
0x180044bd2  push    rdi
0x180044bd3  push    r12
0x180044bd5  push    r14
0x180044bd7  push    r15
0x180044bd9  sub     rsp, 40h
0x180044bdd  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x180044be6  mov     [rsp+68h+arg_0], rbx
0x180044beb  mov     r15, rdx
0x180044bee  mov     rsi, rcx
0x180044bf1  xor     r12d, r12d
0x180044bf4  test    rdx, rdx
0x180044bf7  jz      loc_180044D40
0x180044bfd  cmp     r8, 7FFFFFFFh
0x180044c04  ja      loc_180044D40
0x180044c0a  mov     r9, r8
0x180044c0d  mov     rax, rdx
0x180044c10  test    r8, r8
0x180044c13  jz      short loc_180044C23
0x180044c15  cmp     [rax], r12b
0x180044c18  jz      short loc_180044C23
0x180044c1a  inc     rax
0x180044c1d  sub     r9, 1
0x180044c21  jnz     short loc_180044C15
0x180044c23  mov     rax, r9
0x180044c26  neg     rax
0x180044c29  sbb     ebx, ebx
0x180044c2b  not     ebx
0x180044c2d  and     ebx, 80070057h
0x180044c33  mov     rax, r9
0x180044c36  sub     r8, r9
0x180044c39  neg     rax
0x180044c3c  sbb     r14, r14
0x180044c3f  and     r14, r8
0x180044c42  test    r9, r9
0x180044c45  jnz     short loc_180044C4E
0x180044c47  mov     eax, ebx
0x180044c49  jmp     loc_180044D47
0x180044c4e  lea     r8, ds:2[r14*2]; Size
0x180044c56  mov     rcx, gs:60h
0x180044c5f  mov     edx, 8; Flags
0x180044c64  mov     rcx, [rcx+30h]; HeapHandle
0x180044c68  call    cs:__imp_RtlAllocateHeap
0x180044c6e  mov     rdi, rax
0x180044c71  mov     [rsp+68h+arg_18], rax
0x180044c79  test    rax, rax
0x180044c7c  jnz     short loc_180044CA4
0x180044c7e  mov     ebx, 8007000Eh
0x180044c83  lea     r9, aFailedToAlloca_10; "Failed to allocate memory for StringBuf"...
0x180044c8a  mov     r8d, 4AEh
0x180044c90  lea     rdx, aAppcompatutili_1; "AppCompatUtility::UTF16StringFromASCIIS"...
0x180044c97  lea     ecx, [rax+1]
0x180044c9a  call    AslLogCallPrintf
0x180044c9f  jmp     loc_180044D69
0x180044ca4  mov     [rsp+68h+arg_8], ebx
0x180044ca8  mov     rcx, r12
0x180044cab  test    r14, r14
0x180044cae  jz      short loc_180044CC4
0x180044cb0  mov     al, [r15+rcx]
0x180044cb4  mov     [rdi+rcx*2], al
0x180044cb7  mov     [rdi+rcx*2+1], r12b
0x180044cbc  inc     rcx
0x180044cbf  cmp     rcx, r14
0x180044cc2  jb      short loc_180044CB0
0x180044cc4  mov     [rdi+r14*2], r12w
0x180044cc9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180044ccd  inc     rdx
0x180044cd0  cmp     [rdi+rdx*2], r12w
0x180044cd5  jnz     short loc_180044CCD
0x180044cd7  cmp     rdx, [rsi+18h]
0x180044cdb  ja      short loc_180044D09
0x180044cdd  cmp     qword ptr [rsi+18h], 7
0x180044ce2  jbe     short loc_180044CE9
0x180044ce4  mov     r14, [rsi]
0x180044ce7  jmp     short loc_180044CEC
0x180044ce9  mov     r14, rsi
0x180044cec  mov     [rsi+10h], rdx
0x180044cf0  lea     rbx, [rdx+rdx]
0x180044cf4  mov     r8, rbx; Size
0x180044cf7  mov     rdx, rdi; Src
0x180044cfa  mov     rcx, r14; void *
0x180044cfd  call    memmove_0
0x180044d02  mov     [rbx+r14], r12w
0x180044d07  jmp     short loc_180044D15
0x180044d09  mov     r9, rdi
0x180044d0c  mov     rcx, rsi
0x180044d0f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180044d14  nop
0x180044d15  mov     ebx, r12d
0x180044d18  jmp     short loc_180044D26
0x180044d1a  mov     ebx, [rsp+68h+arg_8]
0x180044d1e  mov     rdi, [rsp+68h+arg_18]
0x180044d26  mov     rcx, gs:60h
0x180044d2f  mov     r8, rdi; P
0x180044d32  xor     edx, edx; Flags
0x180044d34  mov     rcx, [rcx+30h]; HeapHandle
0x180044d38  call    cs:__imp_RtlFreeHeap
0x180044d3e  jmp     short loc_180044D69
0x180044d40  mov     eax, 80070057h
0x180044d45  mov     ebx, eax
0x180044d47  mov     [rsp+68h+var_48], eax
0x180044d4b  lea     r9, aFailedToGetLen; "Failed to get length. [0x%x]"
0x180044d52  mov     r8d, 4A6h
0x180044d58  lea     rdx, aAppcompatutili_1; "AppCompatUtility::UTF16StringFromASCIIS"...
0x180044d5f  mov     ecx, 1
0x180044d64  call    AslLogCallPrintf
0x180044d69  mov     eax, ebx
0x180044d6b  mov     rbx, [rsp+68h+arg_0]
0x180044d70  add     rsp, 40h
0x180044d74  pop     r15
0x180044d76  pop     r14
0x180044d78  pop     r12
0x180044d7a  pop     rdi
0x180044d7b  pop     rsi
0x180044d7c  retn
```
