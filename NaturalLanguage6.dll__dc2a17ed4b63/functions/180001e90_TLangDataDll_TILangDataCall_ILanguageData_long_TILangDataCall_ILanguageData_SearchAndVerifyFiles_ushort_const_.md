# TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::SearchAndVerifyFiles(ushort const *,ushort,ResourceLoader6::ILoadResources *)

- ea: `0x180001e90`
- end: `0x18000228d`
- name: `?SearchAndVerifyFiles@?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@CAPEAV1@PEBGGPEAUILoadResources@ResourceLoader6@@@Z`
- size: `1021`
- prototype: `HMODULE __fastcall(__int64, unsigned __int16, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180001dd0`

## callees

- `0x180001e90`
- `0x180017858`
- `0x180035640`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x180054e8c`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001f48`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800020ef`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800020ef`

## string_xrefs

- `0x1800020c5`: `%s%s%04x.dll`

## pseudocode

```c
HMODULE __fastcall TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::SearchAndVerifyFiles(
        __int64 a1,
        unsigned __int16 a2,
        struct IUnknown *a3)
{
  HMODULE v5; // rsi
  HMODULE LibraryW; // rbx
  FARPROC ProcAddress; // rdi
  int v8; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  int v11; // eax
  HMODULE v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int16 v16; // [rsp+38h] [rbp-3F0h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp-3E8h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-3E0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-3D0h]
  unsigned int v20; // [rsp+60h] [rbp-3C8h]
  __int64 v21; // [rsp+68h] [rbp-3C0h]
  unsigned int v22; // [rsp+70h] [rbp-3B8h]
  __int64 v23; // [rsp+78h] [rbp-3B0h]
  HMODULE v24; // [rsp+80h] [rbp-3A8h]
  _BYTE v25[64]; // [rsp+98h] [rbp-390h] BYREF
  _BYTE v26[64]; // [rsp+D8h] [rbp-350h] BYREF
  _BYTE v27[64]; // [rsp+118h] [rbp-310h] BYREF
  _BYTE v28[64]; // [rsp+158h] [rbp-2D0h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+198h] [rbp-290h] BYREF
  WCHAR LibFileName[264]; // [rsp+1E0h] [rbp-248h] BYREF
  const void *retaddr; // [rsp+428h] [rbp+0h]

  v23 = -2;
  v18[1] = a3;
  v5 = 0;
  if ( a3 )
  {
    hModule = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, __int64, _QWORD, HMODULE *))a3->lpVtbl[3].AddRef)(
           a3,
           a2,
           256,
           0,
           &hModule) >= 0 )
    {
      LibraryW = hModule;
      if ( !hModule )
        return v5;
LABEL_4:
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "LangDataCall");
        if ( !ProcAddress )
        {
          if ( a3 )
            ResourceLoader6::ILoadResources::UnloadModule(a3, LibraryW);
          CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        v18[0] = 0;
        v13 = (HMODULE)operator new(0x30u);
        v5 = v13;
        hModule = v13;
        if ( v13 )
        {
          *(_QWORD *)v13 = &ILangDataBundle::`vftable';
          *((_QWORD *)v13 + 1) = &ILangDataUnloadListener::`vftable';
          *(_QWORD *)v13 = &TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::`vftable'{for `ILangDataBundle'};
          *((_QWORD *)v13 + 1) = &TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::`vftable'{for `ILangDataUnloadListener'};
          *((_QWORD *)v13 + 2) = LibraryW;
          *((_QWORD *)v13 + 4) = ProcAddress;
          *((_QWORD *)v13 + 3) = 0;
          *((_DWORD *)v13 + 10) = 1;
          *((_BYTE *)v13 + 44) = 0;
        }
        else
        {
          v5 = 0;
        }
        hModule = v5;
        v8 = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v18);
        if ( v8 < 0 )
        {
          CNLException::CNLException((CNLException *)v26, v8, retaddr);
          throw (CNLException *)v26;
        }
        *((_QWORD *)v5 + 3) = v18[0];
        LOWORD(v20) = a2;
        HIWORD(v20) = a2;
        v19 = 0x1F80500028003LL;
        v9 = (**(__int64 (__fastcall ***)(_QWORD))v18[0])(v18[0]);
        v10 = v19 - *(_QWORD *)v9;
        if ( v19 == *(_QWORD *)v9 )
          v10 = v20 - (unsigned __int64)*(unsigned int *)(v9 + 8);
        if ( v10 )
        {
          LOWORD(v22) = a2 & 0x3FF;
          HIWORD(v22) = a2 & 0x3FF;
          v21 = 0x1F80500028003LL;
          v14 = (**(__int64 (__fastcall ***)(_QWORD))v18[0])(v18[0]);
          v15 = v21 - *(_QWORD *)v14;
          if ( v21 == *(_QWORD *)v14 )
            v15 = v22 - (unsigned __int64)*(unsigned int *)(v14 + 8);
          if ( v15 )
          {
            CNLException::CNLException((CNLException *)v27, -1053749231, retaddr);
            throw (CNLException *)v27;
          }
        }
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v18[0] + 16LL))(
                v18[0],
                (unsigned __int64)(v5 + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64));
        if ( v11 < 0 )
        {
          CNLException::CNLException((CNLException *)v28, v11, retaddr);
          throw (CNLException *)v28;
        }
        v24 = v5;
        hModule = 0;
      }
      return v5;
    }
    v16 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, _QWORD, __int64, __int16 *))a3->lpVtbl[2].Release)(a3, a2, 256, &v16) >= 0
      && v16 )
    {
      CNLException::CNLException((CNLException *)v25, -2147467259, retaddr);
      throw (CNLException *)v25;
    }
    return 0;
  }
  else
  {
    if ( StringCchPrintfW(LibFileName, 0x105u, L"%s%s%04x.dll", a1, L"NlsData", a2, 0) >= 0 )
    {
      LibraryW = LoadLibraryW(LibFileName);
      goto LABEL_4;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180001e90  mov     rax, rsp
0x180001e93  push    rsi
0x180001e94  push    rdi
0x180001e95  push    r12
0x180001e97  push    r14
0x180001e99  push    r15
0x180001e9b  sub     rsp, 400h
0x180001ea2  mov     [rsp+428h+var_3B0], 0FFFFFFFFFFFFFFFEh
0x180001eab  mov     [rax+20h], rbx
0x180001eaf  mov     rax, cs:__security_cookie
0x180001eb6  xor     rax, rsp
0x180001eb9  mov     [rsp+428h+var_38], rax
0x180001ec1  mov     r14, r8
0x180001ec4  movzx   r15d, dx
0x180001ec8  mov     [rsp+428h+var_3D8], r8
0x180001ecd  xor     r12d, r12d
0x180001ed0  mov     edi, r12d
0x180001ed3  mov     [rsp+428h+var_3F8], r12
0x180001ed8  mov     esi, r12d
0x180001edb  test    r8, r8
0x180001ede  jz      loc_1800020B1
0x180001ee4  mov     [rsp+428h+hModule], r12
0x180001ee9  mov     rax, [r8]
0x180001eec  lea     rcx, [rsp+428h+hModule]
0x180001ef1  mov     [rsp+428h+var_408], rcx
0x180001ef6  xor     r9d, r9d
0x180001ef9  mov     ebx, 100h
0x180001efe  mov     r8d, ebx
0x180001f01  movzx   edx, r15w
0x180001f05  mov     rcx, r14
0x180001f08  mov     rax, [rax+50h]
0x180001f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f11  test    eax, eax
0x180001f13  js      loc_18000212A
0x180001f19  mov     rbx, [rsp+428h+hModule]
0x180001f1e  test    rbx, rbx
0x180001f21  jz      loc_180002081
0x180001f27  cmovnz  edi, r12d
0x180001f2b  mov     [rsp+428h+var_3F8], rdi
0x180001f30  mov     [rsp+428h+var_3F8], rbx
0x180001f35  test    rbx, rbx
0x180001f38  jz      loc_180002081
0x180001f3e  lea     rdx, ProcName; "LangDataCall"
0x180001f45  mov     rcx, rbx; hModule
0x180001f48  call    cs:__imp_GetProcAddress
0x180001f4e  mov     rdi, rax
0x180001f51  test    rax, rax
0x180001f54  jnz     loc_180002102
0x180001f5a  test    r14, r14
0x180001f5d  jnz     loc_180002276
0x180001f63  mov     r8, [rsp+428h]; void *
0x180001f6b  mov     edx, 80004005h; int
0x180001f70  lea     rcx, [rsp+428h+pExceptionObject]; this
0x180001f78  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180001f7d  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180001f84  lea     rcx, [rsp+428h+pExceptionObject]; pExceptionObject
0x180001f8c  call    _CxxThrowException_0
0x180001f92  lea     rax, ??_7ILangDataBundle@@6B@; const ILangDataBundle::`vftable'
0x180001f99  mov     [rsi], rax
0x180001f9c  lea     rax, ??_7ILangDataUnloadListener@@6B@; const ILangDataUnloadListener::`vftable'
0x180001fa3  mov     [rsi+8], rax
0x180001fa7  lea     rax, ??_7?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@6BILangDataBundle@@@; const TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::`vftable'{for `ILangDataBundle'}
0x180001fae  mov     [rsi], rax
0x180001fb1  lea     rax, ??_7?$TLangDataDll@U?$TILangDataCall@VILanguageData@@@@P6AJPEAPEAU1@@Z@@6BILangDataUnloadListener@@@; const TLangDataDll<TILangDataCall<ILanguageData>,long (*)(TILangDataCall<ILanguageData> * *)>::`vftable'{for `ILangDataUnloadListener'}
0x180001fb8  mov     [rsi+8], rax
0x180001fbc  mov     [rsi+10h], rbx
0x180001fc0  mov     [rsi+20h], rdi
0x180001fc4  mov     [rsi+18h], r12
0x180001fc8  mov     dword ptr [rsi+28h], 1
0x180001fcf  mov     [rsi+2Ch], r12b
0x180001fd3  mov     [rsp+428h+hModule], rsi
0x180001fd8  mov     [rsp+428h+var_3F8], r12
0x180001fdd  lea     rcx, [rsp+428h+var_3E0]
0x180001fe2  mov     rax, rdi
0x180001fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fea  test    eax, eax
0x180001fec  js      loc_18000221F
0x180001ff2  mov     rax, [rsp+428h+var_3E0]
0x180001ff7  mov     [rsi+18h], rax
0x180001ffb  mov     word ptr [rsp+428h+var_3C8], r15w
0x180002001  mov     word ptr [rsp+428h+var_3C8+2], r15w
0x180002007  mov     ebx, 28003h
0x18000200c  mov     dword ptr [rsp+428h+var_3D0], ebx
0x180002010  mov     edi, 1F805h
0x180002015  mov     dword ptr [rsp+428h+var_3D0+4], edi
0x180002019  mov     rcx, [rsp+428h+var_3E0]
0x18000201e  mov     rax, [rcx]
0x180002021  mov     rax, [rax]
0x180002024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002029  mov     rcx, [rsp+428h+var_3D0]
0x18000202e  sub     rcx, [rax]
0x180002031  jnz     short loc_18000203D
0x180002033  mov     ecx, [rsp+428h+var_3C8]
0x180002037  mov     eax, [rax+8]
0x18000203a  sub     rcx, rax
0x18000203d  test    rcx, rcx
0x180002040  jnz     loc_18000216B
0x180002046  mov     rcx, [rsp+428h+var_3E0]
0x18000204b  mov     r9, [rcx]
0x18000204e  mov     rax, rsi
0x180002051  lea     r8, [rsi+8]
0x180002055  neg     rax
0x180002058  sbb     rdx, rdx
0x18000205b  and     rdx, r8
0x18000205e  mov     rax, [r9+10h]
0x180002062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002067  test    eax, eax
0x180002069  js      loc_18000224A
0x18000206f  mov     [rsp+428h+hModule], r12
0x180002074  mov     [rsp+428h+var_3A8], rsi
0x18000207c  mov     [rsp+428h+hModule], r12
0x180002081  mov     [rsp+428h+var_3F8], r12
0x180002086  mov     rax, rsi
0x180002089  mov     rcx, [rsp+428h+var_38]
0x180002091  xor     rcx, rsp; StackCookie
0x180002094  call    __security_check_cookie
0x180002099  mov     rbx, [rsp+428h+arg_18]
0x1800020a1  add     rsp, 400h
0x1800020a8  pop     r15
0x1800020aa  pop     r14
0x1800020ac  pop     r12
0x1800020ae  pop     rdi
0x1800020af  pop     rsi
0x1800020b0  retn
0x1800020b1  mov     [rsp+428h+var_400], r15d
0x1800020b6  lea     rax, aNlsdata; "NlsData"
0x1800020bd  mov     [rsp+428h+var_408], rax
0x1800020c2  mov     r9, rcx
0x1800020c5  lea     r8, aSS04xDll; "%s%s%04x.dll"
0x1800020cc  mov     edx, 105h; unsigned __int64
0x1800020d1  lea     rcx, [rsp+428h+LibFileName]; unsigned __int16 *
0x1800020d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800020de  test    eax, eax
0x1800020e0  js      short loc_18000215F
0x1800020e2  mov     [rsp+428h+var_3F8], r12
0x1800020e7  lea     rcx, [rsp+428h+LibFileName]; lpLibFileName
0x1800020ef  call    cs:__imp_LoadLibraryW
0x1800020f5  mov     rbx, rax
0x1800020f8  mov     [rsp+428h+var_3F8], rax
0x1800020fd  jmp     loc_180001F35
0x180002102  mov     [rsp+428h+var_3E0], r12
0x180002107  mov     ecx, 30h ; '0'; Size
0x18000210c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002111  mov     rsi, rax
0x180002114  mov     [rsp+428h+hModule], rax
0x180002119  test    rax, rax
0x18000211c  jnz     loc_180001F92
0x180002122  mov     rsi, r12
0x180002125  jmp     loc_180001FD3
0x18000212a  mov     [rsp+428h+var_3F0], r12w
0x180002130  mov     rax, [r14]
0x180002133  lea     r9, [rsp+428h+var_3F0]
0x180002138  mov     r8d, ebx
0x18000213b  movzx   edx, r15w
0x18000213f  mov     rcx, r14
0x180002142  mov     rax, [rax+40h]
0x180002146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000214b  test    eax, eax
0x18000214d  jns     loc_1800021E4
0x180002153  mov     [rsp+428h+var_3F8], r12
0x180002158  xor     eax, eax
0x18000215a  jmp     loc_180002089
0x18000215f  mov     [rsp+428h+var_3F8], r12
0x180002164  xor     eax, eax
0x180002166  jmp     loc_180002089
0x18000216b  mov     eax, 3FFh
0x180002170  and     r15w, ax
0x180002174  mov     word ptr [rsp+428h+var_3B8], r15w
0x18000217a  mov     word ptr [rsp+428h+var_3B8+2], r15w
0x180002180  mov     dword ptr [rsp+428h+var_3C0], ebx
0x180002184  mov     dword ptr [rsp+428h+var_3C0+4], edi
0x180002188  mov     rcx, [rsp+428h+var_3E0]
0x18000218d  mov     rax, [rcx]
0x180002190  mov     rax, [rax]
0x180002193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002198  mov     rcx, [rsp+428h+var_3C0]
0x18000219d  sub     rcx, [rax]
0x1800021a0  jnz     short loc_1800021AC
0x1800021a2  mov     ecx, [rsp+428h+var_3B8]
0x1800021a6  mov     eax, [rax+8]
0x1800021a9  sub     rcx, rax
0x1800021ac  test    rcx, rcx
0x1800021af  jz      loc_180002046
0x1800021b5  mov     r8, [rsp+428h]; void *
0x1800021bd  mov     edx, 0C1311011h; int
0x1800021c2  lea     rcx, [rsp+428h+var_310]; this
0x1800021ca  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800021cf  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800021d6  lea     rcx, [rsp+428h+var_310]; pExceptionObject
0x1800021de  call    _CxxThrowException_0
0x1800021e4  cmp     [rsp+428h+var_3F0], r12w
0x1800021ea  jz      loc_180002153
0x1800021f0  mov     r8, [rsp+428h]; void *
0x1800021f8  mov     edx, 80004005h; int
0x1800021fd  lea     rcx, [rsp+428h+var_390]; this
0x180002205  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18000220a  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180002211  lea     rcx, [rsp+428h+var_390]; pExceptionObject
0x180002219  call    _CxxThrowException_0
0x18000221f  mov     r8, [rsp+428h]; void *
0x180002227  mov     edx, eax; int
0x180002229  lea     rcx, [rsp+428h+var_350]; this
0x180002231  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180002236  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18000223d  lea     rcx, [rsp+428h+var_350]; pExceptionObject
0x180002245  call    _CxxThrowException_0
0x18000224a  mov     r8, [rsp+428h]; void *
0x180002252  mov     edx, eax; int
0x180002254  lea     rcx, [rsp+428h+var_2D0]; this
0x18000225c  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180002261  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180002268  lea     rcx, [rsp+428h+var_2D0]; pExceptionObject
0x180002270  call    _CxxThrowException_0
0x180002276  mov     rdx, rbx; void *
0x180002279  mov     rcx, r14; this
0x18000227c  call    ?UnloadModule@ILoadResources@ResourceLoader6@@QEAAJPEAX@Z; ResourceLoader6::ILoadResources::UnloadModule(void *)
0x180002281  mov     [rsp+428h+var_3F8], r12
0x180002286  jmp     loc_180001F63
```
