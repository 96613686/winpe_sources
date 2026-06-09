# AhcpStoreInsertAvlEntry

- ea: `0x14004b8ac`
- end: `0x14004ba7d`
- name: `AhcpStoreInsertAvlEntry`
- size: `465`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int128 *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14004b014`
- `0x14004b7e4`

## callees

- `0x140007ad0`
- `0x140007e40`
- `0x14003e364`
- `0x140045d44`
- `0x14004b8ac`
- `0x14004ba84`
- `0x14004bcd0`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004b8f4`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004b8f4`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14004b92d`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14004b92d`

## string_xrefs

- `0x14004b9ef`: `Entry to be inserted already exists.`
- `0x14004ba51`: `Failed to copy item [%x]`

## pseudocode

```c
__int64 __fastcall AhcpStoreInsertAvlEntry(_QWORD *a1, __int64 a2, __int128 *a3, __int64 a4)
{
  __int128 v4; // xmm1
  int v9; // eax
  unsigned int v10; // ebx
  char *inserted; // rax
  char *v12; // rdi
  char *v13; // rcx
  __int64 (__fastcall *v14)(char *); // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v18; // r8
  const char *v19; // r9
  void *v20[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h]
  __int128 v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+68h] [rbp-8h]

  v4 = *a3;
  *a1 = 0;
  v22 = 0;
  v24 = 0;
  v23 = v4;
  Buffer = 0;
  *(_OWORD *)v20 = 0;
  if ( RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)a2, &Buffer) )
  {
    AslLogCallPrintf(1, "AhcpStoreInsertAvlEntry", 771, "Entry to be inserted already exists.");
    v10 = -1073741823;
  }
  else
  {
    v9 = AslUnicodeStringDuplicate((__m128i *)v20, (__int64)a3);
    v10 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, "AhcpStoreInsertAvlEntry", 783, "Failed to duplicate file name [%x]", v9);
    }
    else
    {
      inserted = (char *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)a2, &Buffer, 0x30u, 0);
      v12 = inserted;
      if ( inserted )
      {
        *((_DWORD *)inserted + 4) = 0;
        v13 = inserted + 40;
        *(_OWORD *)(inserted + 24) = *(_OWORD *)v20;
        v14 = *(__int64 (__fastcall **)(char *))(a2 + 136);
        *(_OWORD *)v20 = 0;
        v15 = v14(v13);
        v10 = v15;
        if ( v15 < 0 )
        {
          v18 = 814;
          v19 = "Failed to allocate item buffer [%x]";
        }
        else
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(a2 + 152))(*((_QWORD *)v12 + 5), a4);
          v10 = v15;
          if ( v15 >= 0 )
          {
            *a1 = v12;
            v10 = 0;
            goto LABEL_7;
          }
          v18 = 821;
          v19 = "Failed to copy item [%x]";
        }
        AslLogCallPrintf(1, "AhcpStoreInsertAvlEntry", v18, v19, v15);
        AhcpStoreFreeAvlEntry((PRTL_AVL_TABLE)a2, v12);
      }
      else
      {
        AslLogCallPrintf(1, "AhcpStoreInsertAvlEntry", 797, "Failed to insert an element to the AVL table");
        v10 = -1073741801;
      }
    }
  }
LABEL_7:
  if ( v20[1] )
  {
    memset(v20[1], 66, WORD1(v20[0]));
    AslFree(v16, v20[1]);
  }
  return v10;
}

```

## disassembly

```asm
0x14004b8ac  push    rbp
0x14004b8ae  push    rbx
0x14004b8af  push    rsi
0x14004b8b0  push    rdi
0x14004b8b1  push    r12
0x14004b8b3  push    r14
0x14004b8b5  push    r15
0x14004b8b7  mov     rbp, rsp
0x14004b8ba  sub     rsp, 70h
0x14004b8be  movups  xmm1, xmmword ptr [r8]
0x14004b8c2  mov     qword ptr [rcx], 0
0x14004b8c9  mov     rsi, rdx
0x14004b8cc  xorps   xmm0, xmm0
0x14004b8cf  lea     rdx, [rbp+Buffer]; Buffer
0x14004b8d3  mov     r15, rcx
0x14004b8d6  mov     r12, r9
0x14004b8d9  movups  [rbp+var_20], xmm0
0x14004b8dd  mov     rcx, rsi; Table
0x14004b8e0  mov     rbx, r8
0x14004b8e3  movups  [rbp+var_10], xmm0
0x14004b8e7  movdqu  [rbp+var_20+8], xmm1
0x14004b8ec  movups  [rbp+Buffer], xmm0
0x14004b8f0  movups  xmmword ptr [rbp+var_40], xmm0
0x14004b8f4  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14004b8fb  nop     dword ptr [rax+rax+00h]
0x14004b900  test    rax, rax
0x14004b903  jnz     loc_14004B9EF
0x14004b909  mov     rdx, rbx
0x14004b90c  lea     rcx, [rbp+var_40]
0x14004b910  call    AslUnicodeStringDuplicate
0x14004b915  mov     ebx, eax
0x14004b917  test    eax, eax
0x14004b919  js      loc_14004B9CB
0x14004b91f  xor     r9d, r9d; NewElement
0x14004b922  lea     rdx, [rbp+Buffer]; Buffer
0x14004b926  mov     rcx, rsi; Table
0x14004b929  lea     r8d, [r9+30h]; BufferSize
0x14004b92d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14004b934  nop     dword ptr [rax+rax+00h]
0x14004b939  mov     rdi, rax
0x14004b93c  test    rax, rax
0x14004b93f  jz      loc_14004BA14
0x14004b945  mov     dword ptr [rax+10h], 0
0x14004b94c  lea     rcx, [rdi+28h]
0x14004b950  movups  xmm0, xmmword ptr [rbp+var_40]
0x14004b954  xorps   xmm1, xmm1
0x14004b957  movdqu  xmmword ptr [rax+18h], xmm0
0x14004b95c  mov     rax, [rsi+88h]
0x14004b963  movups  xmmword ptr [rbp+var_40], xmm1
0x14004b967  call    _guard_dispatch_icall
0x14004b96c  mov     ebx, eax
0x14004b96e  test    eax, eax
0x14004b970  js      loc_14004BA3C
0x14004b976  mov     rax, [rsi+98h]
0x14004b97d  mov     rdx, r12
0x14004b980  mov     rcx, [rdi+28h]
0x14004b984  call    _guard_dispatch_icall
0x14004b989  mov     ebx, eax
0x14004b98b  test    eax, eax
0x14004b98d  js      loc_14004BA4B
0x14004b993  mov     [r15], rdi
0x14004b996  xor     ebx, ebx
0x14004b998  mov     rcx, [rbp+var_40+8]; void *
0x14004b99c  test    rcx, rcx
0x14004b99f  jz      short loc_14004B9B9
0x14004b9a1  movzx   r8d, word ptr [rbp+var_40+2]; Size
0x14004b9a6  mov     edx, 42h ; 'B'; Val
0x14004b9ab  call    memset
0x14004b9b0  mov     rdx, [rbp+var_40+8]
0x14004b9b4  call    AslFree
0x14004b9b9  mov     eax, ebx
0x14004b9bb  add     rsp, 70h
0x14004b9bf  pop     r15
0x14004b9c1  pop     r14
0x14004b9c3  pop     r12
0x14004b9c5  pop     rdi
0x14004b9c6  pop     rsi
0x14004b9c7  pop     rbx
0x14004b9c8  pop     rbp
0x14004b9c9  retn
0x14004b9cb  lea     r9, aFailedToDuplic; "Failed to duplicate file name [%x]"
0x14004b9d2  mov     [rsp+70h+var_50], eax
0x14004b9d6  mov     r8d, 30Fh
0x14004b9dc  lea     rdx, aAhcpstoreinser; "AhcpStoreInsertAvlEntry"
0x14004b9e3  mov     ecx, 1
0x14004b9e8  call    AslLogCallPrintf
0x14004b9ed  jmp     short loc_14004B998
0x14004b9ef  lea     r9, aEntryToBeInser; "Entry to be inserted already exists."
0x14004b9f6  mov     r8d, 303h
0x14004b9fc  lea     rdx, aAhcpstoreinser; "AhcpStoreInsertAvlEntry"
0x14004ba03  mov     ecx, 1
0x14004ba08  call    AslLogCallPrintf
0x14004ba0d  mov     ebx, 0C0000001h
0x14004ba12  jmp     short loc_14004B998
0x14004ba14  lea     r9, aFailedToInsert; "Failed to insert an element to the AVL "...
0x14004ba1b  mov     r8d, 31Dh
0x14004ba21  lea     rdx, aAhcpstoreinser; "AhcpStoreInsertAvlEntry"
0x14004ba28  mov     ecx, 1
0x14004ba2d  call    AslLogCallPrintf
0x14004ba32  mov     ebx, 0C0000017h
0x14004ba37  jmp     loc_14004B998
0x14004ba3c  mov     r8d, 32Eh
0x14004ba42  lea     r9, aFailedToAlloca_15; "Failed to allocate item buffer [%x]"
0x14004ba49  jmp     short loc_14004BA58
0x14004ba4b  mov     r8d, 335h
0x14004ba51  lea     r9, aFailedToCopyIt; "Failed to copy item [%x]"
0x14004ba58  lea     rdx, aAhcpstoreinser; "AhcpStoreInsertAvlEntry"
0x14004ba5f  mov     [rsp+70h+var_50], eax
0x14004ba63  mov     ecx, 1
0x14004ba68  call    AslLogCallPrintf
0x14004ba6d  mov     rdx, rdi; Buffer
0x14004ba70  mov     rcx, rsi; Table
0x14004ba73  call    AhcpStoreFreeAvlEntry
0x14004ba78  jmp     loc_14004B998
```
