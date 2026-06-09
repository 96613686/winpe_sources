# pEstimateDiff(ulong,ulong,ulong *,UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,long (*)(ulong,_ESTIMATE_CALLBACK_DATA *),_ESTIMATE_CALLBACK_DATA *)

- ea: `0x18003275c`
- end: `0x180032adb`
- name: `?pEstimateDiff@@YAJKKPEAKPEAVString@UnBCL@@1PEAV?$Hashtable@PEAVString@UnBCL@@K@2@P6AJKPEAU_ESTIMATE_CALLBACK_DATA@@@Z3@Z`
- size: `895`
- prototype: `__int64 __fastcall(int, unsigned int, _DWORD *, int, const struct UnBCL::String *, __int64, __int64 (__fastcall *)(_QWORD, __int64), __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a6fc`
- `0x18003275c`

## callees

- `0x180009e04`
- `0x18000b070`
- `0x18002443c`
- `0x1800251e0`
- `0x18003275c`
- `0x180033180`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a07`
- `WDSCORE!CurrentIP` at `0x180032a0f`
- `WDSCORE!CurrentIP` at `0x180032a0f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032a75`
- `WDSCORE!WdsSetupLogMessageW` at `0x180032a75`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800327b7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032935`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800327b7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180032935`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18003294d`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18003294d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180032925`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180032925`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032968`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180032968`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800329f2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032a97`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800329f2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180032a97`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032911`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003297a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800329a8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180032911`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003297a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800329a8`

## string_xrefs

- `0x180032a52`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`

## pseudocode

```c
__int64 __fastcall pEstimateDiff(
        int a1,
        unsigned int a2,
        _DWORD *a3,
        int a4,
        const struct UnBCL::String *a5,
        __int64 a6,
        __int64 (__fastcall *a7)(_QWORD, __int64),
        __int64 a8)
{
  int v9; // r12d
  void *v10; // rax
  _QWORD *v11; // rdi
  int FileObjects; // esi
  int v13; // r14d
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  int (__fastcall ***v16)(_QWORD); // rcx
  char *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // r12d
  char *v21; // rcx
  _QWORD *v22; // rax
  const struct UnBCL::String *P; // rax
  const struct UnBCL::String *v24; // rsi
  struct UnBCL::String *v25; // rbx
  UnBCL::String *v26; // rax
  __int64 v27; // rbx
  char *v28; // rcx
  _QWORD *v29; // rax
  int v30; // eax
  DWORD LastError; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  void *v37; // [rsp+68h] [rbp-59h] BYREF
  void **v38; // [rsp+70h] [rbp-51h] BYREF
  _QWORD *v39; // [rsp+78h] [rbp-49h]
  __int64 v40; // [rsp+80h] [rbp-41h]
  __int64 (__fastcall *v41)(_QWORD, __int64); // [rsp+88h] [rbp-39h]
  __int64 v42; // [rsp+90h] [rbp-31h]
  _DWORD *v43; // [rsp+98h] [rbp-29h]
  UnBCL::String *v44; // [rsp+A0h] [rbp-21h]
  _BYTE v45[16]; // [rsp+A8h] [rbp-19h] BYREF

  v43 = a3;
  v9 = a1;
  v42 = a6;
  v41 = a7;
  v40 = a8;
  v10 = UnBCL::Object::operator new(0x80u);
  v37 = v10;
  if ( v10 )
    v10 = (void *)UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(v10);
  UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(&v38, v10);
  v11 = v39;
  (*(void (__fastcall **)(_QWORD *, __int64))(*v39 + 40LL))(v39, 1);
  FileObjects = pGetFileObjects(a4, (_DWORD)v11, (_DWORD)a5, a6, 1);
  if ( FileObjects >= 0 )
  {
    v13 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v11 + 88LL))(v11);
    v14 = 0;
    v15 = a2;
    while ( 1 )
    {
      v16 = (int (__fastcall ***)(_QWORD))((char *)v11 + *(int *)(v11[1] + 12LL) + 8);
      if ( (int)v14 >= (**v16)(v16) )
        break;
      v17 = (char *)v11 + *(int *)(v11[1] + 16LL) + 8;
      v18 = *(_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, v14);
      if ( (*(_BYTE *)(v18 + 72) & 0x10) != 0 )
      {
        if ( (*(_DWORD *)(v18 + 72) & 0x400) == 0
          || (v19 = *(_DWORD *)(v18 + 76), v19 < 0) && v19 != -1610612733 && v19 != -1610612724 )
        {
          v20 = v9 + 1;
          if ( v41 )
          {
            FileObjects = v41(v20, v40);
            if ( FileObjects < 0 )
            {
              LastError = GetLastError();
              v32 = CurrentIP();
              v33 = ConstructPartialMsgW(
                      0x2000000,
                      "Received failure from callback, exiting estimation. Error: 0x%08X\n",
                      FileObjects);
              WdsSetupLogMessageW(
                v33,
                0,
                L"D",
                0,
                609,
                L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
                L"pEstimateDiff",
                v32,
                LastError,
                0,
                0);
              v38 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
              UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v38);
              return (unsigned int)FileObjects;
            }
          }
          ++v13;
          if ( v20 < v15 )
          {
            v21 = (char *)v11 + *(int *)(v11[1] + 16LL) + 8;
            v22 = (_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, v14);
            P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*v22 + 24LL);
            v24 = P;
            if ( a5 )
            {
              v25 = UnBCL::Path::Combine(a5, P);
            }
            else
            {
              v26 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              v25 = v26;
              v44 = v26;
              if ( v26 )
              {
                UnBCL::String::String(v26, v24);
                *(_QWORD *)v25 = &UnBCL::String::`local vftable';
              }
              else
              {
                v25 = 0;
              }
            }
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v45, v25);
            LODWORD(v37) = 0;
            v27 = UnBCL::SmartPtr<UnBCL::String>::get_P(v45);
            v28 = (char *)v11 + *(int *)(v11[1] + 16LL) + 8;
            v29 = (_QWORD *)(*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, v14);
            v30 = UnBCL::SmartPtr<UnBCL::String>::get_P(*v29 + 8LL);
            FileObjects = pEstimateDiff(v20, a2, (unsigned int)&v37, v30, v27, v42, (__int64)v41, v40);
            if ( FileObjects < 0 )
            {
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v45);
              break;
            }
            v13 += (int)v37;
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v45);
            v15 = a2;
          }
          v9 = a1;
        }
      }
      ++v14;
    }
    *v43 = v13;
    v38 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v38);
  }
  else
  {
    v38 = &UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)&v38);
  }
  return (unsigned int)FileObjects;
}

```

## disassembly

```asm
0x18003275c  push    rbp
0x18003275e  push    rbx
0x18003275f  push    rsi
0x180032760  push    rdi
0x180032761  push    r12
0x180032763  push    r13
0x180032765  push    r14
0x180032767  push    r15
0x180032769  lea     rbp, [rsp-7]
0x18003276e  sub     rsp, 0C8h
0x180032775  mov     rax, cs:__security_cookie
0x18003277c  xor     rax, rsp
0x18003277f  mov     [rbp+3Fh+var_48], rax
0x180032783  mov     rbx, r9
0x180032786  mov     [rbp+3Fh+var_68], r8
0x18003278a  mov     [rbp+3Fh+var_A0], edx
0x18003278d  mov     r12d, ecx
0x180032790  mov     [rbp+3Fh+var_9C], ecx
0x180032793  mov     r13, [rbp+3Fh+arg_20]
0x180032797  mov     rsi, [rbp+3Fh+arg_28]
0x18003279b  mov     [rbp+3Fh+var_70], rsi
0x18003279f  mov     r9, [rbp+3Fh+arg_30]
0x1800327a3  mov     [rbp+3Fh+var_78], r9
0x1800327a7  mov     rax, [rbp+3Fh+arg_38]
0x1800327ae  mov     [rbp+3Fh+var_80], rax
0x1800327b2  mov     ecx, 80h
0x1800327b7  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800327bd  mov     [rbp+3Fh+var_98], rax
0x1800327c1  test    rax, rax
0x1800327c4  jz      short loc_1800327CF
0x1800327c6  mov     rcx, rax
0x1800327c9  call    ??0?$ArrayList@PEAVCFileObject@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<CFileObject *>::ArrayList<CFileObject *>(void)
0x1800327ce  nop
0x1800327cf  mov     rdx, rax
0x1800327d2  lea     rcx, [rbp+3Fh+var_90]
0x1800327d6  call    ??0?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVCFileObject@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::SmartPtr<UnBCL::ArrayList<CFileObject *>>(UnBCL::ArrayList<CFileObject *> *)
0x1800327db  nop
0x1800327dc  mov     rdi, [rbp+3Fh+var_88]
0x1800327e0  mov     rax, [rdi]
0x1800327e3  mov     r14d, 1
0x1800327e9  mov     edx, r14d
0x1800327ec  mov     rcx, rdi
0x1800327ef  mov     rax, [rax+28h]
0x1800327f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327f8  mov     dword ptr [rsp+100h+var_E0], r14d
0x1800327fd  mov     r9, rsi
0x180032800  mov     r8, r13
0x180032803  mov     rdx, rdi
0x180032806  mov     rcx, rbx
0x180032809  call    ?pGetFileObjects@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVCFileObject@@@2@0PEAV?$Hashtable@PEAVString@UnBCL@@K@2@H@Z; pGetFileObjects(UnBCL::String *,UnBCL::ArrayList<CFileObject *> *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,int)
0x18003280e  mov     esi, eax
0x180032810  test    eax, eax
0x180032812  jns     short loc_18003282E
0x180032814  lea     rcx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x18003281b  mov     [rbp+3Fh+var_90], rcx
0x18003281f  lea     rcx, [rbp+3Fh+var_90]
0x180032823  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032828  nop
0x180032829  jmp     loc_180032AB9
0x18003282e  xor     r14d, r14d
0x180032831  mov     rax, [rdi]
0x180032834  mov     rcx, rdi
0x180032837  mov     rax, [rax+58h]
0x18003283b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032840  xor     r15d, r15d
0x180032843  mov     ebx, [rbp+3Fh+var_A0]
0x180032846  mov     rax, [rdi+8]
0x18003284a  movsxd  rcx, dword ptr [rax+0Ch]
0x18003284e  add     rcx, 8
0x180032852  add     rcx, rdi
0x180032855  mov     rax, [rcx]
0x180032858  mov     rax, [rax]
0x18003285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032860  cmp     r15d, eax
0x180032863  jge     loc_180032A9D
0x180032869  mov     rax, [rdi+8]
0x18003286d  movsxd  rcx, dword ptr [rax+10h]
0x180032871  add     rcx, 8
0x180032875  add     rcx, rdi
0x180032878  mov     rax, [rcx]
0x18003287b  mov     edx, r15d
0x18003287e  mov     rax, [rax+18h]
0x180032882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032887  mov     rax, [rax]
0x18003288a  test    byte ptr [rax+48h], 10h
0x18003288e  jz      loc_1800329FF
0x180032894  test    dword ptr [rax+48h], 400h
0x18003289b  jz      short loc_1800328BE
0x18003289d  mov     eax, [rax+4Ch]
0x1800328a0  test    eax, eax
0x1800328a2  jns     loc_1800329FF
0x1800328a8  cmp     eax, 0A0000003h
0x1800328ad  jz      loc_1800329FF
0x1800328b3  cmp     eax, 0A000000Ch
0x1800328b8  jz      loc_1800329FF
0x1800328be  inc     r12d
0x1800328c1  mov     rax, [rbp+3Fh+var_78]
0x1800328c5  test    rax, rax
0x1800328c8  jz      short loc_1800328E0
0x1800328ca  mov     rdx, [rbp+3Fh+var_80]
0x1800328ce  mov     ecx, r12d
0x1800328d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328d6  mov     esi, eax
0x1800328d8  test    eax, eax
0x1800328da  js      loc_180032A07
0x1800328e0  inc     r14d
0x1800328e3  cmp     r12d, ebx
0x1800328e6  jnb     loc_1800329FB
0x1800328ec  mov     rax, [rdi+8]
0x1800328f0  movsxd  rcx, dword ptr [rax+10h]
0x1800328f4  add     rcx, 8
0x1800328f8  add     rcx, rdi
0x1800328fb  mov     rax, [rcx]
0x1800328fe  mov     edx, r15d
0x180032901  mov     rax, [rax+18h]
0x180032905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003290a  mov     rcx, [rax]
0x18003290d  add     rcx, 18h
0x180032911  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180032917  mov     rsi, rax
0x18003291a  test    r13, r13
0x18003291d  jz      short loc_180032930
0x18003291f  mov     rdx, rax
0x180032922  mov     rcx, r13
0x180032925  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18003292b  mov     rbx, rax
0x18003292e  jmp     short loc_180032961
0x180032930  mov     ecx, 18h
0x180032935  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003293b  mov     rbx, rax
0x18003293e  mov     [rbp+3Fh+var_60], rax
0x180032942  test    rax, rax
0x180032945  jz      short loc_18003295F
0x180032947  mov     rdx, rsi
0x18003294a  mov     rcx, rax
0x18003294d  call    cs:__imp_??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x180032953  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18003295a  mov     [rbx], rax
0x18003295d  jmp     short loc_180032961
0x18003295f  xor     ebx, ebx
0x180032961  mov     rdx, rbx
0x180032964  lea     rcx, [rbp+3Fh+var_58]
0x180032968  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003296e  nop
0x18003296f  mov     dword ptr [rbp+3Fh+var_98], 0
0x180032976  lea     rcx, [rbp+3Fh+var_58]
0x18003297a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180032980  mov     rbx, rax
0x180032983  mov     rcx, [rdi+8]
0x180032987  movsxd  rcx, dword ptr [rcx+10h]
0x18003298b  add     rcx, 8
0x18003298f  add     rcx, rdi
0x180032992  mov     rdx, [rcx]
0x180032995  mov     rax, [rdx+18h]
0x180032999  mov     edx, r15d
0x18003299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329a1  mov     rcx, [rax]
0x1800329a4  add     rcx, 8
0x1800329a8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800329ae  mov     rcx, [rbp+3Fh+var_80]
0x1800329b2  mov     [rsp+100h+var_C8], rcx
0x1800329b7  mov     r9, [rbp+3Fh+var_78]
0x1800329bb  mov     [rsp+100h+var_D0], r9
0x1800329c0  mov     rcx, [rbp+3Fh+var_70]
0x1800329c4  mov     [rsp+100h+var_D8], rcx
0x1800329c9  mov     [rsp+100h+var_E0], rbx
0x1800329ce  mov     r9, rax
0x1800329d1  lea     r8, [rbp+3Fh+var_98]
0x1800329d5  mov     edx, [rbp+3Fh+var_A0]
0x1800329d8  mov     ecx, r12d
0x1800329db  call    ?pEstimateDiff@@YAJKKPEAKPEAVString@UnBCL@@1PEAV?$Hashtable@PEAVString@UnBCL@@K@2@P6AJKPEAU_ESTIMATE_CALLBACK_DATA@@@Z3@Z; pEstimateDiff(ulong,ulong,ulong *,UnBCL::String *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,long (*)(ulong,_ESTIMATE_CALLBACK_DATA *),_ESTIMATE_CALLBACK_DATA *)
0x1800329e0  mov     esi, eax
0x1800329e2  test    eax, eax
0x1800329e4  js      loc_180032A93
0x1800329ea  add     r14d, dword ptr [rbp+3Fh+var_98]
0x1800329ee  lea     rcx, [rbp+3Fh+var_58]
0x1800329f2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800329f8  mov     ebx, [rbp+3Fh+var_A0]
0x1800329fb  mov     r12d, [rbp+3Fh+var_9C]
0x1800329ff  inc     r15d
0x180032a02  jmp     loc_180032846
0x180032a07  call    cs:__imp_GetLastError
0x180032a0d  mov     edi, eax
0x180032a0f  call    cs:__imp_CurrentIP
0x180032a15  mov     rbx, rax
0x180032a18  mov     r8d, esi
0x180032a1b  lea     rdx, aReceivedFailur; "Received failure from callback, exiting"...
0x180032a22  mov     ecx, 2000000h; unsigned int
0x180032a27  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180032a2c  mov     [rsp+100h+var_B0], 0
0x180032a34  mov     [rsp+100h+var_B8], 0
0x180032a3d  mov     [rsp+100h+var_C0], edi
0x180032a41  mov     [rsp+100h+var_C8], rbx
0x180032a46  lea     rcx, aPestimatediff; "pEstimateDiff"
0x180032a4d  mov     [rsp+100h+var_D0], rcx
0x180032a52  lea     rcx, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\pitr\\dll\\src\\r"...
0x180032a59  mov     [rsp+100h+var_D8], rcx
0x180032a5e  mov     dword ptr [rsp+100h+var_E0], 261h
0x180032a66  xor     r9d, r9d
0x180032a69  lea     r8, aD; "D"
0x180032a70  xor     edx, edx
0x180032a72  mov     rcx, rax
0x180032a75  call    cs:__imp_WdsSetupLogMessageW
0x180032a7b  nop
0x180032a7c  lea     rcx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x180032a83  mov     [rbp+3Fh+var_90], rcx
0x180032a87  lea     rcx, [rbp+3Fh+var_90]
0x180032a8b  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032a90  nop
0x180032a91  jmp     short loc_180032AB9
0x180032a93  lea     rcx, [rbp+3Fh+var_58]
0x180032a97  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180032a9d  mov     rax, [rbp+3Fh+var_68]
0x180032aa1  mov     [rax], r14d
0x180032aa4  lea     rcx, ??_7?$SmartPtr@V?$ArrayList@PEAVCFileObject@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<CFileObject *>>::`vftable'
0x180032aab  mov     [rbp+3Fh+var_90], rcx
0x180032aaf  lea     rcx, [rbp+3Fh+var_90]
0x180032ab3  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180032ab8  nop
0x180032ab9  mov     eax, esi
0x180032abb  mov     rcx, [rbp+3Fh+var_48]
0x180032abf  xor     rcx, rsp; StackCookie
0x180032ac2  call    __security_check_cookie
0x180032ac7  add     rsp, 0C8h
0x180032ace  pop     r15
0x180032ad0  pop     r14
0x180032ad2  pop     r13
0x180032ad4  pop     r12
0x180032ad6  pop     rdi
0x180032ad7  pop     rsi
0x180032ad8  pop     rbx
0x180032ad9  pop     rbp
0x180032ada  retn
```
