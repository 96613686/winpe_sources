# CMigrateVCRuntimeShim::CopyVCRuntimeFiles(ushort const *,ushort const *)

- ea: `0x180036384`
- end: `0x180036460`
- name: `?CopyVCRuntimeFiles@CMigrateVCRuntimeShim@@AEAAHPEBG0@Z`
- size: `220`
- prototype: `int(CMigrateVCRuntimeShim *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180035f54`
- `0x180036540`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180036384`
- `0x18004fec8`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180036418`
- `KERNEL32!CopyFileW` at `0x180036418`

## pseudocode

```c
_BOOL8 __fastcall CMigrateVCRuntimeShim::CopyVCRuntimeFiles(
        CMigrateVCRuntimeShim *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // ebx
  __int64 i; // rdi
  size_t v7; // rdx
  size_t v8; // rdx
  BOOL v9; // eax
  int v10; // ecx
  ULONG v12; // [rsp+20h] [rbp-458h]
  ULONG v13; // [rsp+20h] [rbp-458h]
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR pszPathOut[264]; // [rsp+240h] [rbp-238h] BYREF

  v3 = 0;
  for ( i = 0; i != 45; ++i )
  {
    memset_0(pszPathOut, 0, 0x208u);
    memset_0(NewFileName, 0, 0x208u);
    PathCchCombineEx(pszPathOut, v7, a2, off_18006BDD0[i], v12);
    PathCchCombineEx(NewFileName, v8, a3, off_18006BDD0[i], v13);
    v9 = CopyFileW(pszPathOut, NewFileName, 0);
    v10 = v3 + 1;
    if ( !v9 )
      v10 = v3;
    v3 = v10;
  }
  return v10 != 0;
}

```

## disassembly

```asm
0x180036384  mov     [rsp+arg_0], rbx
0x180036389  mov     [rsp+arg_18], rbp
0x18003638e  push    rsi
0x18003638f  push    rdi
0x180036390  push    r14
0x180036392  sub     rsp, 460h
0x180036399  mov     rax, cs:__security_cookie
0x1800363a0  xor     rax, rsp
0x1800363a3  mov     [rsp+478h+var_28], rax
0x1800363ab  xor     ebx, ebx
0x1800363ad  mov     rbp, r8
0x1800363b0  xor     edi, edi
0x1800363b2  mov     rsi, rdx
0x1800363b5  xor     edx, edx; Val
0x1800363b7  lea     rcx, [rsp+478h+pszPathOut]; void *
0x1800363bf  mov     r8d, 208h; Size
0x1800363c5  call    memset_0
0x1800363ca  xor     edx, edx; Val
0x1800363cc  lea     rcx, [rsp+478h+NewFileName]; void *
0x1800363d1  mov     r8d, 208h; Size
0x1800363d7  call    memset_0
0x1800363dc  lea     r14, off_18006BDD0; "msvcp110.dll"
0x1800363e3  mov     r8, rsi; pszPathIn
0x1800363e6  mov     r9, [r14+rdi*8]; pszMore
0x1800363ea  lea     rcx, [rsp+478h+pszPathOut]; pszPathOut
0x1800363f2  call    PathCchCombineEx
0x1800363f7  mov     r9, [r14+rdi*8]; pszMore
0x1800363fb  lea     rcx, [rsp+478h+NewFileName]; pszPathOut
0x180036400  mov     r8, rbp; pszPathIn
0x180036403  call    PathCchCombineEx
0x180036408  xor     r8d, r8d; bFailIfExists
0x18003640b  lea     rdx, [rsp+478h+NewFileName]; lpNewFileName
0x180036410  lea     rcx, [rsp+478h+pszPathOut]; lpExistingFileName
0x180036418  call    cs:__imp_CopyFileW
0x18003641e  test    eax, eax
0x180036420  lea     ecx, [rbx+1]
0x180036423  cmovz   ecx, ebx
0x180036426  inc     rdi
0x180036429  mov     ebx, ecx
0x18003642b  cmp     rdi, 2Dh ; '-'
0x18003642f  jnz     short loc_1800363B5
0x180036431  xor     eax, eax
0x180036433  test    ecx, ecx
0x180036435  setnz   al
0x180036438  mov     rcx, [rsp+478h+var_28]
0x180036440  xor     rcx, rsp; StackCookie
0x180036443  call    __security_check_cookie
0x180036448  lea     r11, [rsp+478h+var_18]
0x180036450  mov     rbx, [r11+20h]
0x180036454  mov     rbp, [r11+38h]
0x180036458  mov     rsp, r11
0x18003645b  pop     r14
0x18003645d  pop     rdi
0x18003645e  pop     rsi
0x18003645f  retn
```
