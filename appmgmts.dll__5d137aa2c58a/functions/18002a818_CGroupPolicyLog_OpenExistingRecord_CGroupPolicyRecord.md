# CGroupPolicyLog::OpenExistingRecord(CGroupPolicyRecord *)

- ea: `0x18002a818`
- end: `0x18002a969`
- name: `?OpenExistingRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(CGroupPolicyLog *__hidden this, struct CGroupPolicyRecord *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b3bc`
- `0x18000f470`

## callees

- `0x18002a818`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a87f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a86e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a87f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a8cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a83c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a891`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a83c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a891`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a8c3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a942`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a942`

## pseudocode

```c
__int64 __fastcall CGroupPolicyLog::OpenExistingRecord(CGroupPolicyLog *this, struct CGroupPolicyRecord *a2)
{
  HLOCAL v4; // rax
  void *v5; // rbx
  int v6; // esi
  void *v7; // rcx
  HLOCAL v9; // rax
  OLECHAR *v10; // rsi
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rbp
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v15 = 260;
  v4 = LocalAlloc(0x40u, 0x208u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v6 = (*(__int64 (__fastcall **)(struct CGroupPolicyRecord *, HLOCAL, unsigned int *))(*(_QWORD *)a2 + 24LL))(
         a2,
         v4,
         &v15);
  v7 = v5;
  if ( v6 < 0 )
  {
LABEL_3:
    LocalFree(v7);
    return (unsigned int)v6;
  }
  if ( v6 )
  {
    LocalFree(v5);
    v9 = LocalAlloc(0x40u, 2LL * v15);
    v5 = v9;
    if ( !v9 )
      return 2147942414LL;
    v6 = (*(__int64 (__fastcall **)(struct CGroupPolicyRecord *, HLOCAL, unsigned int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           v9,
           &v15);
    v7 = v5;
    if ( v6 < 0 )
      goto LABEL_3;
  }
  v10 = SysAllocString((const OLECHAR *)v7);
  LocalFree(v5);
  if ( !v10 )
    return 2147942414LL;
  v11 = *((_QWORD *)this + 4);
  v16 = 0;
  if ( v11 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v11 + 48LL))(
            v11,
            v10,
            0,
            0,
            &v16,
            0);
    if ( v12 >= 0 )
    {
      v13 = *((_QWORD *)a2 + 1);
      v14 = v16;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      *((_QWORD *)a2 + 1) = v14;
    }
  }
  else
  {
    v12 = -2147024882;
  }
  SysFreeString(v10);
  if ( v12 >= 0 )
    *((_DWORD *)a2 + 4) = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002a818  mov     [rsp+arg_0], rbx
0x18002a81d  push    rbp
0x18002a81e  push    rsi
0x18002a81f  push    rdi
0x18002a820  sub     rsp, 40h
0x18002a824  mov     rdi, rdx
0x18002a827  mov     [rsp+58h+arg_10], 104h
0x18002a82f  mov     rbp, rcx
0x18002a832  mov     edx, 208h; uBytes
0x18002a837  mov     ecx, 40h ; '@'; uFlags
0x18002a83c  call    cs:__imp_LocalAlloc
0x18002a842  mov     rbx, rax
0x18002a845  test    rax, rax
0x18002a848  jz      loc_18002A957
0x18002a84e  mov     r8, [rdi]
0x18002a851  mov     rdx, rbx
0x18002a854  mov     rcx, rdi
0x18002a857  mov     rax, [r8+18h]
0x18002a85b  lea     r8, [rsp+58h+arg_10]
0x18002a860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a865  mov     esi, eax
0x18002a867  mov     rcx, rbx; hMem
0x18002a86a  test    eax, eax
0x18002a86c  jns     short loc_18002A87B
0x18002a86e  call    cs:__imp_LocalFree
0x18002a874  mov     eax, esi
0x18002a876  jmp     loc_18002A95C
0x18002a87b  test    esi, esi
0x18002a87d  jz      short loc_18002A8C3
0x18002a87f  call    cs:__imp_LocalFree
0x18002a885  mov     edx, [rsp+58h+arg_10]
0x18002a889  mov     ecx, 40h ; '@'; uFlags
0x18002a88e  add     rdx, rdx; uBytes
0x18002a891  call    cs:__imp_LocalAlloc
0x18002a897  mov     rbx, rax
0x18002a89a  test    rax, rax
0x18002a89d  jz      loc_18002A957
0x18002a8a3  mov     rcx, [rdi]
0x18002a8a6  lea     r8, [rsp+58h+arg_10]
0x18002a8ab  mov     rdx, rbx
0x18002a8ae  mov     rax, [rcx+18h]
0x18002a8b2  mov     rcx, rdi
0x18002a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8ba  mov     esi, eax
0x18002a8bc  mov     rcx, rbx; psz
0x18002a8bf  test    eax, eax
0x18002a8c1  js      short loc_18002A86E
0x18002a8c3  call    cs:__imp_SysAllocString
0x18002a8c9  mov     rcx, rbx; hMem
0x18002a8cc  mov     rsi, rax
0x18002a8cf  call    cs:__imp_LocalFree
0x18002a8d5  test    rsi, rsi
0x18002a8d8  jz      short loc_18002A957
0x18002a8da  mov     rcx, [rbp+20h]
0x18002a8de  mov     [rsp+58h+arg_18], 0
0x18002a8e7  test    rcx, rcx
0x18002a8ea  jz      short loc_18002A93A
0x18002a8ec  mov     rax, [rcx]
0x18002a8ef  lea     rdx, [rsp+58h+arg_18]
0x18002a8f4  mov     [rsp+58h+var_30], 0
0x18002a8fd  xor     r9d, r9d
0x18002a900  mov     [rsp+58h+var_38], rdx
0x18002a905  xor     r8d, r8d
0x18002a908  mov     rdx, rsi
0x18002a90b  mov     rax, [rax+30h]
0x18002a90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a914  mov     ebx, eax
0x18002a916  test    eax, eax
0x18002a918  js      short loc_18002A93F
0x18002a91a  mov     rcx, [rdi+8]
0x18002a91e  mov     rbp, [rsp+58h+arg_18]
0x18002a923  test    rcx, rcx
0x18002a926  jz      short loc_18002A934
0x18002a928  mov     rax, [rcx]
0x18002a92b  mov     rax, [rax+10h]
0x18002a92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a934  mov     [rdi+8], rbp
0x18002a938  jmp     short loc_18002A93F
0x18002a93a  mov     ebx, 8007000Eh
0x18002a93f  mov     rcx, rsi; bstrString
0x18002a942  call    cs:__imp_SysFreeString
0x18002a948  test    ebx, ebx
0x18002a94a  js      short loc_18002A953
0x18002a94c  mov     dword ptr [rdi+10h], 0
0x18002a953  mov     eax, ebx
0x18002a955  jmp     short loc_18002A95C
0x18002a957  mov     eax, 8007000Eh
0x18002a95c  mov     rbx, [rsp+58h+arg_0]
0x18002a961  add     rsp, 40h
0x18002a965  pop     rdi
0x18002a966  pop     rsi
0x18002a967  pop     rbp
0x18002a968  retn
```
