# AppxDestagePackage

- ea: `0x180039df0`
- end: `0x18003a2ec`
- name: `AppxDestagePackage`
- size: `1276`
- prototype: `__int64 __fastcall(char *string)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008a1c`
- `0x18000b644`
- `0x1800140c8`
- `0x180023e8c`
- `0x180031168`
- `0x180039df0`
- `0x18003a2f4`
- `0x180075cb0`
- `0x1800808ac`
- `0x1800863b4`
- `0x1800c5460`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003a097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18003a097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a1fb`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180039e0a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180039e0a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180039e87`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a178`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a2d5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180039e87`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a178`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003a2d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppxDestagePackage(char *string)
{
  int v2; // ebx
  __int64 (__fastcall ***v4)(_QWORD, char *, __int64 *); // r14
  int v5; // edi
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  HSTRING v14; // rdi
  __int64 (__fastcall *v15)(_QWORD, char *, __int64 *); // rsi
  __int64 v16; // rcx
  int v17; // esi
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  __int64 v30; // [rsp+38h] [rbp-38h] BYREF
  HSTRING stringa; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string2; // [rsp+48h] [rbp-28h] BYREF
  __int128 v33; // [rsp+50h] [rbp-20h] BYREF
  int v34; // [rsp+60h] [rbp-10h]
  void *retaddr; // [rsp+A8h] [rbp+38h]
  char v36; // [rsp+B8h] [rbp+48h] BYREF
  __int64 (__fastcall ***result)(_QWORD, char *, __int64 *); // [rsp+C0h] [rbp+50h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+58h] BYREF

  v2 = RoInitialize(1);
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147417850 )
  {
    sub_180008A1C(retaddr, 699, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v2);
    return (unsigned int)v2;
  }
  *(_WORD *)(*(_QWORD *)&qword_1801534C8 + 8LL) = 257;
  sub_1800863B4(&result);
  v4 = result;
  if ( !result )
  {
    v5 = -2147024882;
    sub_180008A1C(retaddr, 710, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", 2147942414LL);
LABEL_6:
    if ( v2 >= 0 )
      RoUninitialize();
    return (unsigned int)v5;
  }
  v29 = 0;
  v6 = (*result)[15](result, string, &v29);
  v5 = v6;
  if ( v6 < 0 )
  {
    sub_180008A1C(retaddr, 715, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v6);
LABEL_11:
    v7 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( v4 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, char *, __int64 *)))(*v4)[2])(v4);
    goto LABEL_6;
  }
  v38 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v38);
  if ( v5 < 0 )
  {
    v8 = 717;
LABEL_17:
    sub_180008A1C(retaddr, v8, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
    goto LABEL_18;
  }
  v36 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 56LL))(v38, &v36);
  if ( v5 < 0 )
  {
    v8 = 720;
    goto LABEL_17;
  }
  if ( !v36 )
  {
    v34 = 0;
    v33 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)string, 0);
    v5 = sub_1800C5460(StringRawBuffer, &v33);
    if ( v5 >= 0 )
    {
      LOBYTE(result) = 0;
      v5 = sub_1800808AC(*((_QWORD *)&v33 + 1), &result);
      if ( v5 >= 0 )
      {
        if ( (_BYTE)result )
        {
          v26 = sub_18003A2F4(*((_QWORD *)&v33 + 1));
          if ( v26 )
            sub_180075CB0(retaddr, 756, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v26);
        }
        Concurrency::details::TaskStack::~TaskStack((Concurrency::details::TaskStack *)&v33);
        goto LABEL_71;
      }
      v25 = 751;
    }
    else
    {
      v25 = 749;
    }
    sub_180008A1C(retaddr, v25, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
    Concurrency::details::TaskStack::~TaskStack((Concurrency::details::TaskStack *)&v33);
LABEL_18:
    v9 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_11;
  }
  v30 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v30);
  v5 = v10;
  if ( v10 < 0 )
  {
    sub_180008A1C(retaddr, 726, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v10);
LABEL_25:
    v11 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_18;
  }
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 64LL))(v38, &v36);
  if ( !v36 )
  {
    stringa = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL))(v30, &stringa);
    v5 = v12;
    if ( v12 < 0 )
    {
      sub_180008A1C(retaddr, 731, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v12);
LABEL_30:
      if ( stringa )
        WindowsDeleteString(stringa);
      goto LABEL_25;
    }
    string2 = 0;
    v13 = sub_180031168(&string2, L"S-1-5-18", 8);
    v5 = v13;
    if ( v13 < 0 )
    {
      sub_180008A1C(retaddr, 733, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v13);
      if ( string2 )
        WindowsDeleteString(string2);
      goto LABEL_30;
    }
    v14 = string2;
    LODWORD(result) = 0;
    WindowsCompareStringOrdinal(stringa, string2, (INT32 *)&result);
    if ( !(_DWORD)result )
    {
      result = 0;
      v15 = (*v4)[8];
      sub_18000B644(&result);
      v17 = v15(v4, string, (__int64 *)&result);
      if ( v17 < 0 )
      {
        v19 = 740;
LABEL_38:
        sub_180008A1C(retaddr, v19, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v17);
        sub_18000B644(&result);
        if ( v14 )
          WindowsDeleteString(v14);
        if ( stringa )
          WindowsDeleteString(stringa);
        v20 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        if ( v4 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, char *, __int64 *)))(*v4)[2])(v4);
        if ( v2 >= 0 )
          RoUninitialize();
        return (unsigned int)v17;
      }
      v17 = sub_180023E8C(v16, result, v18);
      if ( v17 < 0 )
      {
        v19 = 741;
        goto LABEL_38;
      }
      sub_18000B644(&result);
    }
    if ( v14 )
      WindowsDeleteString(v14);
    if ( stringa )
      WindowsDeleteString(stringa);
  }
  v23 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_71:
  v27 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( v4 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, char *, __int64 *)))(*v4)[2])(v4);
  if ( v2 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180039df0  push    rbp
0x180039df2  push    rbx
0x180039df3  push    rsi
0x180039df4  push    rdi
0x180039df5  push    r12
0x180039df7  push    r14
0x180039df9  push    r15
0x180039dfb  mov     rbp, rsp
0x180039dfe  sub     rsp, 70h
0x180039e02  mov     r15, rcx
0x180039e05  mov     ecx, 1
0x180039e0a  call    cs:RoInitialize
0x180039e10  mov     ecx, 80000000h
0x180039e15  mov     ebx, eax
0x180039e17  add     eax, ecx
0x180039e19  test    ecx, eax
0x180039e1b  jnz     short loc_180039E44
0x180039e1d  cmp     ebx, 80010106h
0x180039e23  jz      short loc_180039E44
0x180039e25  mov     rcx, [rbp+38h]
0x180039e29  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180039e30  mov     r9d, ebx
0x180039e33  mov     edx, 2BBh
0x180039e38  call    sub_180008A1C
0x180039e3d  mov     eax, ebx
0x180039e3f  jmp     loc_18003A2DD
0x180039e44  mov     rax, cs:qword_1801534C8
0x180039e4b  lea     rcx, [rbp+result]
0x180039e4f  mov     word ptr [rax+8], 101h
0x180039e55  call    sub_1800863B4
0x180039e5a  mov     r14, [rbp+result]
0x180039e5e  xor     r12d, r12d
0x180039e61  test    r14, r14
0x180039e64  jnz     short loc_180039E94
0x180039e66  mov     rcx, [rbp+38h]
0x180039e6a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180039e71  mov     edi, 8007000Eh
0x180039e76  mov     edx, 2C6h
0x180039e7b  mov     r9d, edi
0x180039e7e  call    sub_180008A1C
0x180039e83  test    ebx, ebx
0x180039e85  js      short loc_180039E8D
0x180039e87  call    cs:RoUninitialize
0x180039e8d  mov     eax, edi
0x180039e8f  jmp     loc_18003A2DD
0x180039e94  mov     [rbp+var_40], r12
0x180039e98  lea     r8, [rbp+var_40]
0x180039e9c  mov     rax, [r14]
0x180039e9f  mov     rdx, r15
0x180039ea2  mov     rcx, r14
0x180039ea5  mov     rax, [rax+78h]
0x180039ea9  call    j__guard_dispatch_icall
0x180039eae  mov     edi, eax
0x180039eb0  test    eax, eax
0x180039eb2  jns     short loc_180039EFB
0x180039eb4  mov     rcx, [rbp+38h]
0x180039eb8  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180039ebf  mov     r9d, eax
0x180039ec2  mov     edx, 2CBh
0x180039ec7  call    sub_180008A1C
0x180039ecc  mov     rcx, [rbp+var_40]
0x180039ed0  test    rcx, rcx
0x180039ed3  jz      short loc_180039EE5
0x180039ed5  mov     [rbp+var_40], r12
0x180039ed9  mov     rax, [rcx]
0x180039edc  mov     rax, [rax+10h]
0x180039ee0  call    j__guard_dispatch_icall
0x180039ee5  test    r14, r14
0x180039ee8  jz      short loc_180039E83
0x180039eea  mov     rax, [r14]
0x180039eed  mov     rcx, r14
0x180039ef0  mov     rax, [rax+10h]
0x180039ef4  call    j__guard_dispatch_icall
0x180039ef9  jmp     short loc_180039E83
0x180039efb  mov     rcx, [rbp+var_40]
0x180039eff  lea     rdx, [rbp+arg_18]
0x180039f03  mov     [rbp+arg_18], r12
0x180039f07  mov     rax, [rcx]
0x180039f0a  mov     rax, [rax+30h]
0x180039f0e  call    j__guard_dispatch_icall
0x180039f13  mov     edi, eax
0x180039f15  test    eax, eax
0x180039f17  jns     short loc_180039F4C
0x180039f19  mov     edx, 2CDh
0x180039f1e  mov     rcx, [rbp+38h]
0x180039f22  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180039f29  mov     r9d, edi
0x180039f2c  call    sub_180008A1C
0x180039f31  mov     rcx, [rbp+arg_18]
0x180039f35  test    rcx, rcx
0x180039f38  jz      short loc_180039ECC
0x180039f3a  mov     [rbp+arg_18], r12
0x180039f3e  mov     rax, [rcx]
0x180039f41  mov     rax, [rax+10h]
0x180039f45  call    j__guard_dispatch_icall
0x180039f4a  jmp     short loc_180039ECC
0x180039f4c  mov     rcx, [rbp+arg_18]
0x180039f50  lea     rdx, [rbp+arg_8]
0x180039f54  mov     [rbp+arg_8], r12b
0x180039f58  mov     rax, [rcx]
0x180039f5b  mov     rax, [rax+38h]
0x180039f5f  call    j__guard_dispatch_icall
0x180039f64  mov     edi, eax
0x180039f66  test    eax, eax
0x180039f68  jns     short loc_180039F71
0x180039f6a  mov     edx, 2D0h
0x180039f6f  jmp     short loc_180039F1E
0x180039f71  cmp     [rbp+arg_8], r12b
0x180039f75  jz      loc_18003A1EB
0x180039f7b  mov     rcx, [rbp+arg_18]
0x180039f7f  lea     rdx, [rbp+var_38]
0x180039f83  mov     [rbp+var_38], r12
0x180039f87  mov     rax, [rcx]
0x180039f8a  mov     rax, [rax+30h]
0x180039f8e  call    j__guard_dispatch_icall
0x180039f93  mov     edi, eax
0x180039f95  test    eax, eax
0x180039f97  jns     short loc_180039FD3
0x180039f99  mov     rcx, [rbp+38h]
0x180039f9d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180039fa4  mov     r9d, eax
0x180039fa7  mov     edx, 2D6h
0x180039fac  call    sub_180008A1C
0x180039fb1  mov     rcx, [rbp+var_38]
0x180039fb5  test    rcx, rcx
0x180039fb8  jz      loc_180039F31
0x180039fbe  mov     [rbp+var_38], r12
0x180039fc2  mov     rax, [rcx]
0x180039fc5  mov     rax, [rax+10h]
0x180039fc9  call    j__guard_dispatch_icall
0x180039fce  jmp     loc_180039F31
0x180039fd3  mov     rcx, [rbp+arg_18]
0x180039fd7  lea     rdx, [rbp+arg_8]
0x180039fdb  mov     rax, [rcx]
0x180039fde  mov     rax, [rax+40h]
0x180039fe2  call    j__guard_dispatch_icall
0x180039fe7  cmp     [rbp+arg_8], r12b
0x180039feb  jnz     loc_18003A1C9
0x180039ff1  mov     rcx, [rbp+var_38]
0x180039ff5  lea     rdx, [rbp+string]
0x180039ff9  mov     [rbp+string], r12
0x180039ffd  mov     rax, [rcx]
0x18003a000  mov     rax, [rax+30h]
0x18003a004  call    j__guard_dispatch_icall
0x18003a009  mov     edi, eax
0x18003a00b  test    eax, eax
0x18003a00d  jns     short loc_18003A03B
0x18003a00f  mov     rcx, [rbp+38h]
0x18003a013  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18003a01a  mov     r9d, eax
0x18003a01d  mov     edx, 2DBh
0x18003a022  call    sub_180008A1C
0x18003a027  mov     rcx, [rbp+string]; string
0x18003a02b  test    rcx, rcx
0x18003a02e  jz      short loc_180039FB1
0x18003a030  call    cs:WindowsDeleteString
0x18003a036  jmp     loc_180039FB1
0x18003a03b  mov     r8d, 8
0x18003a041  mov     [rbp+string2], r12
0x18003a045  lea     rdx, aS1518; "S-1-5-18"
0x18003a04c  lea     rcx, [rbp+string2]
0x18003a050  call    sub_180031168
0x18003a055  mov     edi, eax
0x18003a057  test    eax, eax
0x18003a059  jns     short loc_18003A084
0x18003a05b  mov     rcx, [rbp+38h]
0x18003a05f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18003a066  mov     r9d, eax
0x18003a069  mov     edx, 2DDh
0x18003a06e  call    sub_180008A1C
0x18003a073  mov     rcx, [rbp+string2]; string
0x18003a077  test    rcx, rcx
0x18003a07a  jz      short loc_18003A027
0x18003a07c  call    cs:WindowsDeleteString
0x18003a082  jmp     short loc_18003A027
0x18003a084  mov     rdi, [rbp+string2]
0x18003a088  lea     r8, [rbp+result]; result
0x18003a08c  mov     rcx, [rbp+string]; string1
0x18003a090  mov     rdx, rdi; string2
0x18003a093  mov     dword ptr [rbp+result], r12d
0x18003a097  call    cs:WindowsCompareStringOrdinal
0x18003a09d  cmp     dword ptr [rbp+result], r12d
0x18003a0a1  jnz     loc_18003A1AC
0x18003a0a7  mov     [rbp+result], r12
0x18003a0ab  lea     rcx, [rbp+result]
0x18003a0af  mov     rax, [r14]
0x18003a0b2  mov     rsi, [rax+40h]
0x18003a0b6  call    sub_18000B644
0x18003a0bb  lea     r8, [rbp+result]
0x18003a0bf  mov     rdx, r15
0x18003a0c2  mov     rcx, r14
0x18003a0c5  mov     rax, rsi
0x18003a0c8  call    j__guard_dispatch_icall
0x18003a0cd  mov     esi, eax
0x18003a0cf  test    eax, eax
0x18003a0d1  jns     loc_18003A185
0x18003a0d7  mov     edx, 2E4h
0x18003a0dc  mov     rcx, [rbp+38h]
0x18003a0e0  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18003a0e7  mov     r9d, esi
0x18003a0ea  call    sub_180008A1C
0x18003a0ef  lea     rcx, [rbp+result]
0x18003a0f3  call    sub_18000B644
0x18003a0f8  test    rdi, rdi
0x18003a0fb  jz      short loc_18003A106
0x18003a0fd  mov     rcx, rdi; string
0x18003a100  call    cs:WindowsDeleteString
0x18003a106  mov     rcx, [rbp+string]; string
0x18003a10a  test    rcx, rcx
0x18003a10d  jz      short loc_18003A115
0x18003a10f  call    cs:WindowsDeleteString
0x18003a115  mov     rcx, [rbp+var_38]
0x18003a119  test    rcx, rcx
0x18003a11c  jz      short loc_18003A12E
0x18003a11e  mov     [rbp+var_38], r12
0x18003a122  mov     rax, [rcx]
0x18003a125  mov     rax, [rax+10h]
0x18003a129  call    j__guard_dispatch_icall
0x18003a12e  mov     rcx, [rbp+arg_18]
0x18003a132  test    rcx, rcx
0x18003a135  jz      short loc_18003A147
0x18003a137  mov     [rbp+arg_18], r12
0x18003a13b  mov     rax, [rcx]
0x18003a13e  mov     rax, [rax+10h]
0x18003a142  call    j__guard_dispatch_icall
0x18003a147  mov     rcx, [rbp+var_40]
0x18003a14b  test    rcx, rcx
0x18003a14e  jz      short loc_18003A160
0x18003a150  mov     [rbp+var_40], r12
0x18003a154  mov     rax, [rcx]
0x18003a157  mov     rax, [rax+10h]
0x18003a15b  call    j__guard_dispatch_icall
0x18003a160  test    r14, r14
0x18003a163  jz      short loc_18003A174
0x18003a165  mov     rax, [r14]
0x18003a168  mov     rcx, r14
0x18003a16b  mov     rax, [rax+10h]
0x18003a16f  call    j__guard_dispatch_icall
0x18003a174  test    ebx, ebx
0x18003a176  js      short loc_18003A17E
0x18003a178  call    cs:RoUninitialize
0x18003a17e  mov     eax, esi
0x18003a180  jmp     loc_18003A2DD
0x18003a185  mov     rdx, [rbp+result]
0x18003a189  mov     [rsp+70h+var_50], r12
0x18003a18e  call    sub_180023E8C
0x18003a193  mov     esi, eax
0x18003a195  test    eax, eax
0x18003a197  jns     short loc_18003A1A3
0x18003a199  mov     edx, 2E5h
0x18003a19e  jmp     loc_18003A0DC
0x18003a1a3  lea     rcx, [rbp+result]
0x18003a1a7  call    sub_18000B644
0x18003a1ac  test    rdi, rdi
0x18003a1af  jz      short loc_18003A1BA
0x18003a1b1  mov     rcx, rdi; string
0x18003a1b4  call    cs:WindowsDeleteString
0x18003a1ba  mov     rcx, [rbp+string]; string
0x18003a1be  test    rcx, rcx
0x18003a1c1  jz      short loc_18003A1C9
0x18003a1c3  call    cs:WindowsDeleteString
0x18003a1c9  mov     rcx, [rbp+var_38]
0x18003a1cd  test    rcx, rcx
0x18003a1d0  jz      loc_18003A28B
0x18003a1d6  mov     [rbp+var_38], r12
0x18003a1da  mov     rax, [rcx]
0x18003a1dd  mov     rax, [rax+10h]
0x18003a1e1  call    j__guard_dispatch_icall
0x18003a1e6  jmp     loc_18003A28B
0x18003a1eb  xorps   xmm0, xmm0
0x18003a1ee  mov     [rbp+var_10], r12d
0x18003a1f2  xor     edx, edx; length
0x18003a1f4  mov     rcx, r15; string
0x18003a1f7  movups  [rbp+var_20], xmm0
0x18003a1fb  call    cs:WindowsGetStringRawBuffer
0x18003a201  mov     rcx, rax
0x18003a204  lea     rdx, [rbp+var_20]
0x18003a208  call    sub_1800C5460
0x18003a20d  mov     edi, eax
0x18003a20f  test    eax, eax
0x18003a211  jns     short loc_18003A239
0x18003a213  mov     edx, 2EDh
0x18003a218  mov     rcx, [rbp+38h]
0x18003a21c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18003a223  mov     r9d, edi
0x18003a226  call    sub_180008A1C
0x18003a22b  lea     rcx, [rbp+var_20]; this
0x18003a22f  call    ??1TaskStack@details@Concurrency@@QEAA@XZ; Concurrency::details::TaskStack::~TaskStack(void)
0x18003a234  jmp     loc_180039F31
0x18003a239  mov     rcx, qword ptr [rbp+var_20+8]
0x18003a23d  lea     rdx, [rbp+result]
0x18003a241  mov     byte ptr [rbp+result], r12b
0x18003a245  call    sub_1800808AC
0x18003a24a  mov     edi, eax
0x18003a24c  test    eax, eax
0x18003a24e  jns     short loc_18003A257
0x18003a250  mov     edx, 2EFh
0x18003a255  jmp     short loc_18003A218
0x18003a257  cmp     byte ptr [rbp+result], r12b
0x18003a25b  jz      short loc_18003A282
  ... truncated ...
```
