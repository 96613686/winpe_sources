# CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_

- ea: `0x180007a64`
- end: `0x180007c1b`
- name: `CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000593c`
- `0x180007a64`

## callees

- `0x180007a64`
- `0x1800386f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ab8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ab8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b81`

## pseudocode

```c
int __fastcall CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  char *v10; // r15
  __int64 v11; // rdi
  __int64 v12; // r13
  unsigned __int64 v13; // r12
  int v14; // ecx
  int v15; // eax
  __int64 v17; // [rsp+30h] [rbp-68h]
  char *v18; // [rsp+38h] [rbp-60h]
  unsigned __int64 v19; // [rsp+40h] [rbp-58h]
  char v20; // [rsp+B8h] [rbp+20h]

  LODWORD(v8) = a4 - 1;
  if ( a4 != 1 )
  {
    if ( a4 == 2 )
    {
      LODWORD(v8) = CompareStringOrdinal(
                      *(LPCWCH *)(*(_QWORD *)(*(_QWORD *)a1 + 8 * a3) + 8LL),
                      -1,
                      *(LPCWCH *)(*(_QWORD *)(*(_QWORD *)a1 + 8 * a3 + 8) + 8LL),
                      -1,
                      0);
      if ( (_DWORD)v8 == 3 )
      {
        **(_QWORD **)(a1 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 8 * a3);
        *(_QWORD *)(*(_QWORD *)a1 + 8 * a3) = *(_QWORD *)(*(_QWORD *)a1 + 8 * a3 + 8);
        v8 = **(_QWORD **)(a1 + 16);
        *(_QWORD *)(*(_QWORD *)a1 + 8 * a3 + 8) = v8;
      }
    }
    else
    {
      v9 = a4 >> 1;
      v19 = a4 >> 1;
      CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_(
        a1,
        a2,
        a3,
        a4 >> 1);
      CTSimpleArray_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd::unique_ptr_StateRepoHelpers::ExplorerCommandVerb_wistd::default_delete_StateRepoHelpers::ExplorerCommandVerb_______::_MergeSort__CStorageProviderRootsCache::InitializeContextMenuVerbs_::_2_::SortById_(
        a1,
        a2,
        v9 + a3,
        a4 - v9);
      v10 = (char *)(*(_QWORD *)a1 + 8 * a3);
      memcpy_0(*(void **)(a1 + 16), v10, 8 * v9);
      v11 = 0;
      v12 = 0;
      v20 = 0;
      v13 = a4 >> 1;
      do
      {
        v17 = 8 * v12;
        v18 = &v10[8 * v13];
        v14 = CompareStringOrdinal(
                *(LPCWCH *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v12) + 8LL),
                -1,
                *(LPCWCH *)(*(_QWORD *)v18 + 8LL),
                -1,
                0);
        if ( v14 == 1 )
          v15 = -1;
        else
          v15 = v14 == 3;
        if ( v15 > 0 )
        {
          ++v13;
          v8 = *(_QWORD *)v18;
          *(_QWORD *)&v10[8 * v11] = *(_QWORD *)v18;
          if ( v13 == a4 )
          {
            LODWORD(v8) = (unsigned int)memcpy_0(
                                          &v10[8 * v11 + 8],
                                          (const void *)(*(_QWORD *)(a1 + 16) + v17),
                                          8 * (a4 - (v11 + 1)));
            v20 = 1;
          }
        }
        else
        {
          v8 = *(_QWORD *)(a1 + 16);
          ++v12;
          *(_QWORD *)&v10[8 * v11] = *(_QWORD *)(v17 + v8);
          if ( v12 == v19 )
            return v8;
        }
        ++v11;
      }
      while ( !v20 );
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180007a64  push    rbx
0x180007a66  push    rbp
0x180007a67  push    rsi
0x180007a68  push    rdi
0x180007a69  push    r12
0x180007a6b  push    r13
0x180007a6d  push    r14
0x180007a6f  push    r15
0x180007a71  sub     rsp, 58h
0x180007a75  mov     rax, r9
0x180007a78  mov     rbp, r9
0x180007a7b  mov     rdi, r8
0x180007a7e  mov     rsi, rdx
0x180007a81  mov     rbx, rcx
0x180007a84  sub     rax, 1
0x180007a88  jz      loc_180007BB3
0x180007a8e  cmp     rax, 1
0x180007a92  jnz     short loc_180007AF5
0x180007a94  mov     rax, [rcx]
0x180007a97  or      esi, 0FFFFFFFFh
0x180007a9a  mov     r9d, esi; cchCount2
0x180007a9d  mov     [rsp+98h+bIgnoreCase], 0; bIgnoreCase
0x180007aa5  mov     edx, esi; cchCount1
0x180007aa7  mov     r8, [rax+r8*8+8]
0x180007aac  mov     rcx, [rax+rdi*8]
0x180007ab0  mov     r8, [r8+8]; lpString2
0x180007ab4  mov     rcx, [rcx+8]; lpString1
0x180007ab8  call    cs:__imp_CompareStringOrdinal
0x180007abe  cmp     eax, 3
0x180007ac1  jnz     loc_180007BB3
0x180007ac7  mov     rax, [rbx]
0x180007aca  mov     rcx, [rbx+10h]
0x180007ace  mov     rax, [rax+rdi*8]
0x180007ad2  mov     [rcx], rax
0x180007ad5  mov     rcx, [rbx]
0x180007ad8  mov     rax, [rcx+rdi*8+8]
0x180007add  mov     [rcx+rdi*8], rax
0x180007ae1  mov     rax, [rbx+10h]
0x180007ae5  mov     rcx, [rbx]
0x180007ae8  mov     rax, [rax]
0x180007aeb  mov     [rcx+rdi*8+8], rax
0x180007af0  jmp     loc_180007BB3
0x180007af5  mov     r14, rbp
0x180007af8  shr     r14, 1
0x180007afb  mov     r9, r14
0x180007afe  mov     [rsp+98h+var_58], r14
0x180007b03  call    CTSimpleArray_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb__________MergeSort__CStorageProviderRootsCache__InitializeContextMenuVerbs____2___SortById_
0x180007b08  mov     r9, rbp
0x180007b0b  lea     r8, [r14+rdi]
0x180007b0f  sub     r9, r14
0x180007b12  mov     rdx, rsi
0x180007b15  mov     rcx, rbx
0x180007b18  call    CTSimpleArray_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb____4294967294_CTPolicyCoTaskMem_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardCompareHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb______CSimpleArrayStandardMergeHelper_wistd__unique_ptr_StateRepoHelpers__ExplorerCommandVerb_wistd__default_delete_StateRepoHelpers__ExplorerCommandVerb__________MergeSort__CStorageProviderRootsCache__InitializeContextMenuVerbs____2___SortById_
0x180007b1d  mov     rax, [rbx]
0x180007b20  lea     r8, ds:0[r14*8]; Size
0x180007b28  mov     rcx, [rbx+10h]; void *
0x180007b2c  lea     r15, [rax+rdi*8]
0x180007b30  mov     rdx, r15; Src
0x180007b33  call    memcpy_0
0x180007b38  xor     edi, edi
0x180007b3a  xor     r13d, r13d
0x180007b3d  mov     [rsp+98h+arg_18], dil
0x180007b45  or      esi, 0FFFFFFFFh
0x180007b48  mov     r12, r14
0x180007b4b  lea     rax, [r15+r12*8]
0x180007b4f  mov     [rsp+98h+bIgnoreCase], 0; bIgnoreCase
0x180007b57  mov     r8, [rax]
0x180007b5a  lea     rcx, ds:0[r13*8]
0x180007b62  mov     [rsp+98h+var_68], rcx
0x180007b67  mov     r9d, esi; cchCount2
0x180007b6a  mov     [rsp+98h+var_60], rax
0x180007b6f  mov     edx, esi; cchCount1
0x180007b71  mov     rax, [rbx+10h]
0x180007b75  mov     r8, [r8+8]; lpString2
0x180007b79  mov     rcx, [rax+rcx]
0x180007b7d  mov     rcx, [rcx+8]; lpString1
0x180007b81  call    cs:__imp_CompareStringOrdinal
0x180007b87  mov     ecx, eax
0x180007b89  cmp     eax, 1
0x180007b8c  jnz     short loc_180007BD7
0x180007b8e  mov     eax, esi
0x180007b90  lea     r14, [rdi+1]
0x180007b94  test    eax, eax
0x180007b96  jg      short loc_180007BE1
0x180007b98  mov     rax, [rbx+10h]
0x180007b9c  inc     r13
0x180007b9f  mov     rcx, [rsp+98h+var_68]
0x180007ba4  mov     rcx, [rcx+rax]
0x180007ba8  mov     [r15+rdi*8], rcx
0x180007bac  cmp     r13, [rsp+98h+var_58]
0x180007bb1  jnz     short loc_180007BC4
0x180007bb3  add     rsp, 58h
0x180007bb7  pop     r15
0x180007bb9  pop     r14
0x180007bbb  pop     r13
0x180007bbd  pop     r12
0x180007bbf  pop     rdi
0x180007bc0  pop     rsi
0x180007bc1  pop     rbp
0x180007bc2  pop     rbx
0x180007bc3  retn
0x180007bc4  cmp     [rsp+98h+arg_18], 0
0x180007bcc  mov     rdi, r14
0x180007bcf  jz      loc_180007B4B
0x180007bd5  jmp     short loc_180007BB3
0x180007bd7  xor     eax, eax
0x180007bd9  cmp     ecx, 3
0x180007bdc  setz    al
0x180007bdf  jmp     short loc_180007B90
0x180007be1  mov     rax, [rsp+98h+var_60]
0x180007be6  inc     r12
0x180007be9  mov     rax, [rax]
0x180007bec  mov     [r15+rdi*8], rax
0x180007bf0  cmp     r12, rbp
0x180007bf3  jnz     short loc_180007BC4
0x180007bf5  mov     rdx, [rsp+98h+var_68]
0x180007bfa  lea     rcx, [r15+r14*8]; void *
0x180007bfe  add     rdx, [rbx+10h]; Src
0x180007c02  mov     r8, rbp
0x180007c05  sub     r8, r14
0x180007c08  shl     r8, 3; Size
0x180007c0c  call    memcpy_0
0x180007c11  mov     [rsp+98h+arg_18], 1
0x180007c19  jmp     short loc_180007BC4
```
