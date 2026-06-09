# Windows::Globalization::Spelling::ReadWordsFromFileMapping

- ea: `0x140010d08`
- end: `0x1400110e4`
- name: `Windows::Globalization::Spelling::ReadWordsFromFileMapping`
- size: `988`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400110f0`

## callees

- `0x14000e94c`
- `0x14000ec30`
- `0x140010b38`
- `0x140010d08`
- `0x140011110`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400110ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400110ac`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140010ea5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140010d83`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140010d83`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140010ed6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140010ed6`

## pseudocode

```c
_QWORD *__fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping(_QWORD *a1, __int64 a2, char a3)
{
  __int64 v6; // rdx
  HANDLE v7; // rdi
  _BYTE *v8; // r8
  _QWORD *v9; // rcx
  _QWORD *v10; // rdx
  char *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rdx
  _WORD *v15; // rdi
  __int64 v16; // r9
  _BYTE *v17; // r8
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  char *v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rdx
  _QWORD *WordsFromStream; // rdi
  __int64 v25; // rcx
  __int64 v26; // rcx
  void *v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+40h] [rbp-C0h]
  _BYTE v30[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v31; // [rsp+60h] [rbp-A0h]
  _BYTE v32[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v33; // [rsp+80h] [rbp-80h]
  _QWORD *v34; // [rsp+88h] [rbp-78h]
  _QWORD v35[3]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v36; // [rsp+A8h] [rbp-58h]
  _QWORD v37[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v38; // [rsp+C8h] [rbp-38h]
  _WORD *v39; // [rsp+D0h] [rbp-30h] BYREF
  char v40; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-10h]
  HANDLE hFileMappingObject; // [rsp+F8h] [rbp-8h] BYREF
  char v43; // [rsp+100h] [rbp+0h] BYREF
  __int64 v44; // [rsp+118h] [rbp+18h]

  v34 = a1;
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
  v29 = 1;
  v37[0] = &std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  v37[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
  v38 = v37;
  v7 = OpenFileMappingW(4u, 0, *(LPCWSTR *)a2);
  v8 = 0;
  v31 = 0;
  v9 = v38;
  if ( v38 )
  {
    if ( v38 == v37 )
    {
      v8 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))(*v38 + 8LL))(v38, v30);
      v31 = v8;
      v9 = v38;
      if ( !v38 )
        goto LABEL_7;
      v10 = v37;
      LOBYTE(v10) = v38 != v37;
      (*(void (__fastcall **)(_QWORD *, _QWORD *, _BYTE *))(*v38 + 32LL))(v38, v10, v8);
      v8 = v31;
    }
    else
    {
      v8 = v38;
      v31 = v38;
    }
    v9 = 0;
    v38 = 0;
  }
LABEL_7:
  hFileMappingObject = v7;
  v44 = 0;
  if ( v8 )
  {
    if ( v8 == v30 )
      v11 = &v43;
    else
      v11 = 0;
    v12 = (**(__int64 (__fastcall ***)(_BYTE *, char *))v8)(v8, v11);
    v8 = v31;
    v9 = v38;
    v44 = v12;
  }
  else
  {
    v44 = 0;
  }
  if ( v8 )
  {
    LOBYTE(v6) = v8 != v30;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v8 + 32LL))(v8, v6);
    v9 = v38;
  }
  if ( v9 )
  {
    v13 = v37;
    LOBYTE(v13) = v9 != v37;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v13);
    v38 = 0;
  }
  if ( hFileMappingObject != (HANDLE)-1LL )
  {
    v35[0] = &std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
    v35[1] = UnmapViewOfFile;
    v36 = v35;
    v15 = MapViewOfFile(hFileMappingObject, 4u, 0, 0, 0);
    v17 = 0;
    v33 = 0;
    v18 = v36;
    if ( v36 )
    {
      if ( v36 != v35 )
      {
        v17 = v36;
        v33 = v36;
        goto LABEL_23;
      }
      v17 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *))(*v36 + 8LL))(v36, v32);
      v33 = v17;
      v18 = v36;
      if ( v36 )
      {
        v19 = v35;
        LOBYTE(v19) = v36 != v35;
        (*(void (__fastcall **)(_QWORD *, _QWORD *, _BYTE *))(*v36 + 32LL))(v36, v19, v17);
        v17 = v33;
LABEL_23:
        v18 = 0;
        v36 = 0;
      }
    }
    v39 = v15;
    v41 = 0;
    if ( v17 )
    {
      if ( v17 == v32 )
        v20 = &v40;
      else
        v20 = 0;
      v21 = (**(__int64 (__fastcall ***)(_BYTE *, char *))v17)(v17, v20);
      v17 = v33;
      v18 = v36;
      v41 = v21;
    }
    else
    {
      v41 = 0;
    }
    if ( v17 )
    {
      LOBYTE(v14) = v17 != v32;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v17 + 32LL))(v17, v14);
      v18 = v36;
    }
    if ( v18 )
    {
      v22 = v35;
      LOBYTE(v22) = v18 != v35;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v18 + 32LL))(v18, v22);
      v36 = 0;
    }
    v23 = (__int64)v39;
    if ( v39 && *v39 == 0xFEFF )
    {
      LOBYTE(v16) = a3;
      WordsFromStream = (_QWORD *)Windows::Globalization::Spelling::ReadWordsFromStream(
                                    v28,
                                    v39 + 1,
                                    (*(_QWORD *)(a2 + 8) >> 1) - 1LL,
                                    v16);
      if ( a1 != WordsFromStream )
      {
        std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
          (__int64)a1,
          *(__int64 **)(*a1 + 8LL));
        *(_QWORD *)(*a1 + 8LL) = *a1;
        *(_QWORD *)*a1 = *a1;
        *(_QWORD *)(*a1 + 16LL) = *a1;
        a1[1] = 0;
        v25 = *a1;
        *a1 = *WordsFromStream;
        *WordsFromStream = v25;
        v26 = a1[1];
        a1[1] = WordsFromStream[1];
        WordsFromStream[1] = v26;
      }
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
        (__int64)v28,
        *((__int64 **)v28[0] + 1));
      *((void **)v28[0] + 1) = v28[0];
      *(_QWORD *)v28[0] = v28[0];
      *((void **)v28[0] + 2) = v28[0];
      v28[1] = 0;
      operator delete(v28[0]);
    }
    std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(
      (__int64 *)&v39,
      v23);
  }
  std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(
    (__int64 *)&hFileMappingObject,
    v6);
  return a1;
}

```

## disassembly

```asm
0x140010d08  push    rbp
0x140010d0a  push    rbx
0x140010d0b  push    rsi
0x140010d0c  push    rdi
0x140010d0d  push    r14
0x140010d0f  lea     rbp, [rsp-30h]
0x140010d14  sub     rsp, 130h
0x140010d1b  mov     rax, cs:__security_cookie
0x140010d22  xor     rax, rsp
0x140010d25  mov     [rbp+50h+var_30], rax
0x140010d29  mov     r14b, r8b
0x140010d2c  mov     rsi, rdx
0x140010d2f  mov     rbx, rcx
0x140010d32  mov     [rbp+50h+var_C8], rcx
0x140010d36  mov     [rsp+150h+var_110], 0
0x140010d3e  mov     qword ptr [rcx], 0
0x140010d45  mov     qword ptr [rcx+8], 0
0x140010d4d  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x140010d52  mov     [rbx], rax
0x140010d55  mov     [rsp+150h+var_110], 1
0x140010d5d  lea     rax, ??_7?$_Func_impl@U?$_Callable_fun@Q6AHPEAX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEAXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEAXU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x140010d64  mov     [rbp+50h+var_A0], rax
0x140010d68  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x140010d6f  mov     [rbp+50h+var_98], rax
0x140010d73  lea     rax, [rbp+50h+var_A0]
0x140010d77  mov     [rbp+50h+var_88], rax
0x140010d7b  mov     r8, [rsi]; lpName
0x140010d7e  xor     edx, edx; bInheritHandle
0x140010d80  lea     ecx, [rdx+4]; dwDesiredAccess
0x140010d83  call    cs:__imp_OpenFileMappingW
0x140010d89  mov     rdi, rax
0x140010d8c  xor     r8d, r8d
0x140010d8f  mov     [rsp+150h+var_F0], r8
0x140010d94  mov     rcx, [rbp+50h+var_88]
0x140010d98  test    rcx, rcx
0x140010d9b  jz      short loc_140010DF3
0x140010d9d  lea     rax, [rbp+50h+var_A0]
0x140010da1  cmp     rcx, rax
0x140010da4  jnz     short loc_140010DE5
0x140010da6  mov     rax, [rcx]
0x140010da9  lea     rdx, [rsp+150h+var_108]
0x140010dae  mov     rax, [rax+8]
0x140010db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010db7  mov     r8, rax
0x140010dba  mov     [rsp+150h+var_F0], rax
0x140010dbf  mov     rcx, [rbp+50h+var_88]
0x140010dc3  test    rcx, rcx
0x140010dc6  jz      short loc_140010DF3
0x140010dc8  mov     rax, [rcx]
0x140010dcb  lea     rdx, [rbp+50h+var_A0]
0x140010dcf  cmp     rcx, rdx
0x140010dd2  setnz   dl
0x140010dd5  mov     rax, [rax+20h]
0x140010dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dde  mov     r8, [rsp+150h+var_F0]
0x140010de3  jmp     short loc_140010DED
0x140010de5  mov     r8, rcx
0x140010de8  mov     [rsp+150h+var_F0], rcx
0x140010ded  xor     ecx, ecx
0x140010def  mov     [rbp+50h+var_88], rcx
0x140010df3  mov     [rbp+50h+hFileMappingObject], rdi
0x140010df7  mov     [rbp+50h+var_38], 0
0x140010dff  test    r8, r8
0x140010e02  jnz     short loc_140010E0A
0x140010e04  mov     [rbp+50h+var_38], r8
0x140010e08  jmp     short loc_140010E37
0x140010e0a  mov     rax, [r8]
0x140010e0d  mov     rax, [rax]
0x140010e10  lea     rcx, [rsp+150h+var_108]
0x140010e15  cmp     r8, rcx
0x140010e18  mov     rcx, r8
0x140010e1b  jnz     short loc_140010E23
0x140010e1d  lea     rdx, [rbp+50h+var_50]
0x140010e21  jmp     short loc_140010E25
0x140010e23  xor     edx, edx
0x140010e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e2a  mov     r8, [rsp+150h+var_F0]
0x140010e2f  mov     rcx, [rbp+50h+var_88]
0x140010e33  mov     [rbp+50h+var_38], rax
0x140010e37  test    r8, r8
0x140010e3a  jz      short loc_140010E5A
0x140010e3c  mov     rax, [r8]
0x140010e3f  lea     rcx, [rsp+150h+var_108]
0x140010e44  cmp     r8, rcx
0x140010e47  setnz   dl
0x140010e4a  mov     rcx, r8
0x140010e4d  mov     rax, [rax+20h]
0x140010e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e56  mov     rcx, [rbp+50h+var_88]
0x140010e5a  test    rcx, rcx
0x140010e5d  jz      short loc_140010E7B
0x140010e5f  mov     rax, [rcx]
0x140010e62  lea     rdx, [rbp+50h+var_A0]
0x140010e66  cmp     rcx, rdx
0x140010e69  setnz   dl
0x140010e6c  mov     rax, [rax+20h]
0x140010e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e75  xor     ecx, ecx
0x140010e77  mov     [rbp+50h+var_88], rcx
0x140010e7b  test    rcx, rcx
0x140010e7e  jz      short loc_140010E97
0x140010e80  mov     rax, [rcx]
0x140010e83  lea     rdx, [rbp+50h+var_A0]
0x140010e87  cmp     rcx, rdx
0x140010e8a  setnz   dl
0x140010e8d  mov     rax, [rax+20h]
0x140010e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e96  nop
0x140010e97  mov     rcx, [rbp+50h+hFileMappingObject]; hFileMappingObject
0x140010e9b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140010e9f  jz      loc_1400110BD
0x140010ea5  mov     rax, cs:__imp_UnmapViewOfFile
0x140010eac  lea     r8, ??_7?$_Func_impl@U?$_Callable_fun@Q6AHPEBX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEBXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEBXU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x140010eb3  mov     [rbp+50h+var_C0], r8
0x140010eb7  mov     [rbp+50h+var_B8], rax
0x140010ebb  lea     rax, [rbp+50h+var_C0]
0x140010ebf  mov     [rbp+50h+var_A8], rax
0x140010ec3  mov     [rsp+150h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x140010ecc  xor     r9d, r9d; dwFileOffsetLow
0x140010ecf  xor     r8d, r8d; dwFileOffsetHigh
0x140010ed2  lea     edx, [r9+4]; dwDesiredAccess
0x140010ed6  call    cs:__imp_MapViewOfFile
0x140010edc  mov     rdi, rax
0x140010edf  xor     r8d, r8d
0x140010ee2  mov     [rbp+50h+var_D0], r8
0x140010ee6  mov     rcx, [rbp+50h+var_A8]
0x140010eea  test    rcx, rcx
0x140010eed  jz      short loc_140010F42
0x140010eef  lea     rax, [rbp+50h+var_C0]
0x140010ef3  cmp     rcx, rax
0x140010ef6  jnz     short loc_140010F35
0x140010ef8  mov     rax, [rcx]
0x140010efb  lea     rdx, [rsp+150h+var_E8]
0x140010f00  mov     rax, [rax+8]
0x140010f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f09  mov     r8, rax
0x140010f0c  mov     [rbp+50h+var_D0], rax
0x140010f10  mov     rcx, [rbp+50h+var_A8]
0x140010f14  test    rcx, rcx
0x140010f17  jz      short loc_140010F42
0x140010f19  mov     rax, [rcx]
0x140010f1c  lea     rdx, [rbp+50h+var_C0]
0x140010f20  cmp     rcx, rdx
0x140010f23  setnz   dl
0x140010f26  mov     rax, [rax+20h]
0x140010f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f2f  mov     r8, [rbp+50h+var_D0]
0x140010f33  jmp     short loc_140010F3C
0x140010f35  mov     r8, rcx
0x140010f38  mov     [rbp+50h+var_D0], rcx
0x140010f3c  xor     ecx, ecx
0x140010f3e  mov     [rbp+50h+var_A8], rcx
0x140010f42  mov     [rbp+50h+var_80], rdi
0x140010f46  mov     [rbp+50h+var_60], 0
0x140010f4e  test    r8, r8
0x140010f51  jnz     short loc_140010F59
0x140010f53  mov     [rbp+50h+var_60], r8
0x140010f57  jmp     short loc_140010F85
0x140010f59  mov     rax, [r8]
0x140010f5c  mov     rax, [rax]
0x140010f5f  lea     rcx, [rsp+150h+var_E8]
0x140010f64  cmp     r8, rcx
0x140010f67  mov     rcx, r8
0x140010f6a  jnz     short loc_140010F72
0x140010f6c  lea     rdx, [rbp+50h+var_78]
0x140010f70  jmp     short loc_140010F74
0x140010f72  xor     edx, edx
0x140010f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f79  mov     r8, [rbp+50h+var_D0]
0x140010f7d  mov     rcx, [rbp+50h+var_A8]
0x140010f81  mov     [rbp+50h+var_60], rax
0x140010f85  test    r8, r8
0x140010f88  jz      short loc_140010FA8
0x140010f8a  mov     rax, [r8]
0x140010f8d  lea     rcx, [rsp+150h+var_E8]
0x140010f92  cmp     r8, rcx
0x140010f95  setnz   dl
0x140010f98  mov     rcx, r8
0x140010f9b  mov     rax, [rax+20h]
0x140010f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fa4  mov     rcx, [rbp+50h+var_A8]
0x140010fa8  test    rcx, rcx
0x140010fab  jz      short loc_140010FC9
0x140010fad  mov     rax, [rcx]
0x140010fb0  lea     rdx, [rbp+50h+var_C0]
0x140010fb4  cmp     rcx, rdx
0x140010fb7  setnz   dl
0x140010fba  mov     rax, [rax+20h]
0x140010fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fc3  xor     ecx, ecx
0x140010fc5  mov     [rbp+50h+var_A8], rcx
0x140010fc9  test    rcx, rcx
0x140010fcc  jz      short loc_140010FEC
0x140010fce  mov     rax, [rcx]
0x140010fd1  lea     rdx, [rbp+50h+var_C0]
0x140010fd5  cmp     rcx, rdx
0x140010fd8  setnz   dl
0x140010fdb  mov     rax, [rax+20h]
0x140010fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010fe4  mov     [rbp+50h+var_A8], 0
0x140010fec  mov     rdx, [rbp+50h+var_80]
0x140010ff0  test    rdx, rdx
0x140010ff3  jz      loc_1400110B3
0x140010ff9  mov     eax, 0FEFFh
0x140010ffe  cmp     [rdx], ax
0x140011001  jnz     loc_1400110B3
0x140011007  mov     r8, [rsi+8]
0x14001100b  shr     r8, 1
0x14001100e  dec     r8
0x140011011  add     rdx, 2
0x140011015  mov     r9b, r14b
0x140011018  lea     rcx, [rsp+150h+var_120]
0x14001101d  call    Windows__Globalization__Spelling__ReadWordsFromStream
0x140011022  mov     rdi, rax
0x140011025  cmp     rbx, rax
0x140011028  jz      short loc_140011071
0x14001102a  mov     rdx, [rbx]
0x14001102d  mov     rdx, [rdx+8]
0x140011031  mov     rcx, rbx
0x140011034  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x140011039  mov     rcx, [rbx]
0x14001103c  mov     [rcx+8], rcx
0x140011040  mov     rcx, [rbx]
0x140011043  mov     [rcx], rcx
0x140011046  mov     rax, [rbx]
0x140011049  mov     [rax+10h], rax
0x14001104d  mov     qword ptr [rbx+8], 0
0x140011055  mov     rcx, [rbx]
0x140011058  mov     rax, [rdi]
0x14001105b  mov     [rbx], rax
0x14001105e  mov     [rdi], rcx
0x140011061  mov     rcx, [rbx+8]
0x140011065  mov     rax, [rdi+8]
0x140011069  mov     [rbx+8], rax
0x14001106d  mov     [rdi+8], rcx
0x140011071  mov     rdx, [rsp+150h+var_120]
0x140011076  mov     rdx, [rdx+8]
0x14001107a  lea     rcx, [rsp+150h+var_120]
0x14001107f  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x140011084  mov     rax, [rsp+150h+var_120]
0x140011089  mov     [rax+8], rax
0x14001108d  mov     rax, [rsp+150h+var_120]
0x140011092  mov     [rax], rax
0x140011095  mov     rax, [rsp+150h+var_120]
0x14001109a  mov     [rax+10h], rax
0x14001109e  mov     [rsp+150h+var_118], 0
0x1400110a7  mov     rcx, [rsp+150h+var_120]
0x1400110ac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400110b2  nop
0x1400110b3  lea     rcx, [rbp+50h+var_80]
0x1400110b7  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x1400110bc  nop
0x1400110bd  lea     rcx, [rbp+50h+hFileMappingObject]
0x1400110c1  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x1400110c6  mov     rax, rbx
0x1400110c9  mov     rcx, [rbp+50h+var_30]
0x1400110cd  xor     rcx, rsp; StackCookie
0x1400110d0  call    __security_check_cookie
0x1400110d5  add     rsp, 130h
0x1400110dc  pop     r14
0x1400110de  pop     rdi
0x1400110df  pop     rsi
0x1400110e0  pop     rbx
0x1400110e1  pop     rbp
0x1400110e2  retn
```
