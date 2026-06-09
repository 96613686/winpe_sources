# GetSearchFolderName(HINSTANCE__ *,uint,IScope *,IShellItemArray *,ushort * *)

- ea: `0x180019218`
- end: `0x180019307`
- name: `?GetSearchFolderName@@YAJPEAUHINSTANCE__@@IPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z`
- size: `239`
- prototype: `__int64 __usercall@<rax>(HINSTANCE hInstance@<rcx>, unsigned int@<edx>, struct IScope *@<r8>, struct IShellItemArray *@<r9>, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013e0c`
- `0x18003ceec`

## callees

- `0x180006900`
- `0x18000eec0`
- `0x1800120a4`
- `0x180019218`
- `0x18001d0f8`
- `0x180020760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019298`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192dc`

## pseudocode

```c
__int64 __fastcall GetSearchFolderName(
        HINSTANCE hInstance,
        __int64 a2,
        struct IScope *a3,
        struct IShellItemArray *a4,
        unsigned __int16 **a5)
{
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  void *v10; // r8
  enum _SIGDN v12; // [rsp+20h] [rbp-668h]
  LPVOID pv; // [rsp+30h] [rbp-658h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-648h] BYREF
  unsigned __int16 v15[520]; // [rsp+250h] [rbp-438h] BYREF

  pv = 0;
  *a5 = 0;
  v7 = SHDisplayNameFromScopeAndSubQueries(a3, a4, (unsigned int)a3, (unsigned int)a4, v12, (LPWSTR *)&pv);
  if ( v7 >= 0 )
  {
    if ( (unsigned int)_IsScopeSearchHome(a3) )
    {
      v10 = pv;
    }
    else
    {
      if ( !LoadStringW(hInstance, 0x8554u, Buffer, 260) )
      {
        v7 = -2147467259;
LABEL_8:
        CoTaskMemFree(pv);
        return (unsigned int)v7;
      }
      StringCchPrintfW(v15, 0x208u, Buffer, pv);
      v10 = v15;
    }
    v7 = _AllocString<CTCoAllocPolicy>(v9, v8, (__int64)v10);
    goto LABEL_8;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019218  mov     [rsp+arg_8], rbx
0x18001921d  push    rbp
0x18001921e  push    rsi
0x18001921f  push    rdi
0x180019220  sub     rsp, 670h
0x180019227  mov     rax, cs:__security_cookie
0x18001922e  xor     rax, rsp
0x180019231  mov     [rsp+688h+var_28], rax
0x180019239  mov     rdi, [rsp+688h+arg_20]
0x180019241  lea     rax, [rsp+688h+pv]
0x180019246  mov     rbp, rcx
0x180019249  mov     [rsp+688h+pv], 0
0x180019252  mov     rdx, r9; struct IShellItemArray *
0x180019255  mov     [rsp+688h+ppwsz], rax; ppwsz
0x18001925a  mov     rcx, r8; struct IScope *
0x18001925d  mov     rsi, r8
0x180019260  mov     qword ptr [rdi], 0
0x180019267  call    ?SHDisplayNameFromScopeAndSubQueries@@YAJPEAUIScope@@PEAUIShellItemArray@@KKW4_SIGDN@@PEAPEAG@Z; SHDisplayNameFromScopeAndSubQueries(IScope *,IShellItemArray *,ulong,ulong,_SIGDN,ushort * *)
0x18001926c  mov     ebx, eax
0x18001926e  test    eax, eax
0x180019270  js      short loc_1800192E2
0x180019272  mov     rcx, rsi; struct IScope *
0x180019275  call    ?_IsScopeSearchHome@@YAHPEAUIScope@@@Z; _IsScopeSearchHome(IScope *)
0x18001927a  test    eax, eax
0x18001927c  jz      short loc_180019285
0x18001927e  mov     r8, [rsp+688h+pv]
0x180019283  jmp     short loc_1800192CD
0x180019285  mov     r9d, 104h; cchBufferMax
0x18001928b  lea     r8, [rsp+688h+Buffer]; lpBuffer
0x180019290  mov     edx, 8554h; uID
0x180019295  mov     rcx, rbp; hInstance
0x180019298  call    cs:__imp_LoadStringW
0x18001929e  test    eax, eax
0x1800192a0  jnz     short loc_1800192A9
0x1800192a2  mov     ebx, 80004005h
0x1800192a7  jmp     short loc_1800192D7
0x1800192a9  mov     r9, [rsp+688h+pv]
0x1800192ae  lea     r8, [rsp+688h+Buffer]; unsigned __int16 *
0x1800192b3  mov     edx, 208h; unsigned __int64
0x1800192b8  lea     rcx, [rsp+688h+var_438]; unsigned __int16 *
0x1800192c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800192c5  lea     r8, [rsp+688h+var_438]
0x1800192cd  mov     r9, rdi
0x1800192d0  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800192d5  mov     ebx, eax
0x1800192d7  mov     rcx, [rsp+688h+pv]; pv
0x1800192dc  call    cs:__imp_CoTaskMemFree
0x1800192e2  mov     eax, ebx
0x1800192e4  mov     rcx, [rsp+688h+var_28]
0x1800192ec  xor     rcx, rsp; StackCookie
0x1800192ef  call    __security_check_cookie
0x1800192f4  mov     rbx, [rsp+688h+arg_8]
0x1800192fc  add     rsp, 670h
0x180019303  pop     rdi
0x180019304  pop     rsi
0x180019305  pop     rbp
0x180019306  retn
```
