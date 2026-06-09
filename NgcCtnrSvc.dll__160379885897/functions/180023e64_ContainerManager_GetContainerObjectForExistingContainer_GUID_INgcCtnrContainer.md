# ContainerManager::GetContainerObjectForExistingContainer(_GUID,INgcCtnrContainer * *)

- ea: `0x180023e64`
- end: `0x1800240a2`
- name: `?GetContainerObjectForExistingContainer@ContainerManager@@QEAAJU_GUID@@PEAPEAUINgcCtnrContainer@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(ContainerManager *this, struct _GUID *, struct INgcCtnrContainer **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c4fc`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000c688`
- `0x180020378`
- `0x180023278`
- `0x180023a88`
- `0x180023e64`
- `0x180029980`
- `0x18002c640`
- `0x18002d518`
- `0x180055e5c`
- `0x1800596a8`
- `0x18005971c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023fe0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024081`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023fe0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024081`

## string_xrefs

- `0x180023ebf`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180023f1d`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180023f93`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180023eeb`: `Container.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ContainerManager::GetContainerObjectForExistingContainer(
        ContainerManager *this,
        struct _GUID *a2,
        struct INgcCtnrContainer **a3)
{
  unsigned __int16 *v6; // r8
  unsigned int v7; // r9d
  int StringFromGuid; // eax
  unsigned int v9; // ebx
  int DoesFileExist; // eax
  bool *v11; // r8
  __int64 v12; // rdx
  NgcUtils **v13; // rcx
  int started; // eax
  LPVOID v15; // rcx
  NgcUtils *v16; // rcx
  struct INgcCtnrContainer *v17; // rax
  LPVOID v19; // rcx
  int ppv; // [rsp+20h] [rbp-79h]
  unsigned __int16 v21; // [rsp+30h] [rbp-69h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v23[3]; // [rsp+40h] [rbp-59h] BYREF
  NgcUtils *v24[5]; // [rsp+58h] [rbp-41h] BYREF
  struct _GUID v25; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v22 = 0;
  memset_0(&v25, 0, 0x4Eu);
  StringFromGuid = NgcUtils::GetStringFromGuid((NgcUtils *)a2, &v25, v6, v7);
  v9 = StringFromGuid;
  if ( StringFromGuid >= 0 )
  {
    if ( *((_QWORD *)this + 3) > 7u )
      this = *(ContainerManager **)this;
    v23[0] = this;
    v23[1] = &v25;
    v23[2] = L"Container.json";
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v24);
    DoesFileExist = NgcUtils::ComposePath(v23, 3, v24);
    v9 = DoesFileExist;
    if ( DoesFileExist >= 0 )
    {
      LOBYTE(v21) = 0;
      v13 = v24;
      if ( v24[3] > (NgcUtils *)7 )
        v13 = (NgcUtils **)v24[0];
      DoesFileExist = NgcUtils::DoesFileExist((const WCHAR *)v13, &v21, v11);
      v9 = DoesFileExist;
      if ( DoesFileExist >= 0 )
      {
        if ( (_BYTE)v21 )
        {
          if ( (((unsigned __int64)ProcessHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            started = StartTrustlet();
            if ( started < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x18D,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
                (const char *)(unsigned int)started,
                ppv);
          }
          v15 = v22;
          v22 = 0;
          if ( v15 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
          DoesFileExist = CoCreateInstance(
                            &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
                            0,
                            1u,
                            &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
                            &v22);
          v9 = DoesFileExist;
          if ( DoesFileExist < 0 )
          {
            v12 = 405;
            goto LABEL_7;
          }
          NgcUtils::IsSecureBioEnabled(v16);
        }
        else
        {
          v19 = v22;
          v22 = 0;
          if ( v19 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
          DoesFileExist = CoCreateInstance(
                            &GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317,
                            0,
                            1u,
                            &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
                            &v22);
          v9 = DoesFileExist;
          if ( DoesFileExist < 0 )
          {
            v12 = 419;
            goto LABEL_7;
          }
        }
        v17 = (struct INgcCtnrContainer *)v22;
        v22 = 0;
        *a3 = v17;
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v24);
        v9 = 0;
        goto LABEL_22;
      }
      v12 = 386;
    }
    else
    {
      v12 = 378;
    }
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      (const char *)(unsigned int)DoesFileExist,
      ppv);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v24);
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16D,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
    (const char *)(unsigned int)StringFromGuid,
    ppv);
LABEL_22:
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v22);
  return v9;
}

```

## disassembly

```asm
0x180023e64  mov     [rsp-8+arg_18], rbx
0x180023e69  push    rbp
0x180023e6a  push    rsi
0x180023e6b  push    rdi
0x180023e6c  lea     rbp, [rsp-47h]
0x180023e71  sub     rsp, 0E0h
0x180023e78  mov     rax, cs:__security_cookie
0x180023e7f  xor     rax, rsp
0x180023e82  mov     [rbp+57h+var_20], rax
0x180023e86  mov     rsi, r8
0x180023e89  mov     rbx, rdx
0x180023e8c  mov     rdi, rcx
0x180023e8f  mov     [rbp+57h+var_B8], 0
0x180023e97  xor     edx, edx; Val
0x180023e99  lea     r8d, [rdx+4Eh]; Size
0x180023e9d  lea     rcx, [rbp+57h+var_70]; void *
0x180023ea1  call    memset_0
0x180023ea6  lea     rdx, [rbp+57h+var_70]; struct _GUID *
0x180023eaa  mov     rcx, rbx; this
0x180023ead  call    ?GetStringFromGuid@NgcUtils@@YAJAEBU_GUID@@PEAGK@Z; NgcUtils::GetStringFromGuid(_GUID const &,ushort *,ulong)
0x180023eb2  mov     ebx, eax
0x180023eb4  test    eax, eax
0x180023eb6  jns     short loc_180023ED5
0x180023eb8  mov     rcx, [rbp+5Fh]; this
0x180023ebc  mov     r9d, eax; char *
0x180023ebf  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180023ec6  mov     edx, 16Dh; void *
0x180023ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ed0  jmp     loc_18002401B
0x180023ed5  cmp     qword ptr [rdi+18h], 7
0x180023eda  jbe     short loc_180023EDF
0x180023edc  mov     rdi, [rdi]
0x180023edf  mov     [rbp+57h+var_B0], rdi
0x180023ee3  lea     rax, [rbp+57h+var_70]
0x180023ee7  mov     [rbp+57h+var_A8], rax
0x180023eeb  lea     rax, aContainerJson; "Container.json"
0x180023ef2  mov     [rbp+57h+var_A0], rax
0x180023ef6  lea     rcx, [rbp+57h+var_98]
0x180023efa  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180023eff  nop
0x180023f00  lea     r8, [rbp+57h+var_98]
0x180023f04  mov     edx, 3
0x180023f09  lea     rcx, [rbp+57h+var_B0]
0x180023f0d  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180023f12  mov     ebx, eax
0x180023f14  test    eax, eax
0x180023f16  jns     short loc_180023F3F
0x180023f18  mov     edx, 17Ah; void *
0x180023f1d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180023f24  mov     r9d, eax; char *
0x180023f27  mov     rcx, [rbp+5Fh]; this
0x180023f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f30  nop
0x180023f31  lea     rcx, [rbp+57h+var_98]
0x180023f35  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180023f3a  jmp     loc_18002401B
0x180023f3f  mov     byte ptr [rbp+57h+var_C0], 0
0x180023f43  lea     rcx, [rbp+57h+var_98]
0x180023f47  cmp     [rbp+57h+var_80], 7
0x180023f4c  cmova   rcx, [rbp+57h+var_98]; this
0x180023f51  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x180023f55  call    ?DoesFileExist@NgcUtils@@YAJPEBGPEA_N@Z; NgcUtils::DoesFileExist(ushort const *,bool *)
0x180023f5a  mov     ebx, eax
0x180023f5c  test    eax, eax
0x180023f5e  jns     short loc_180023F67
0x180023f60  mov     edx, 182h
0x180023f65  jmp     short loc_180023F1D
0x180023f67  cmp     byte ptr [rbp+57h+var_C0], 0
0x180023f6b  jz      loc_180024046
0x180023f71  mov     rax, cs:ProcessHandle
0x180023f78  inc     rax
0x180023f7b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023f81  jnz     short loc_180023FA5
0x180023f83  call    ?StartTrustlet@@YAJXZ; StartTrustlet(void)
0x180023f88  mov     rcx, [rbp+5Fh]; this
0x180023f8c  test    eax, eax
0x180023f8e  jns     short loc_180023FA5
0x180023f90  mov     r9d, eax; char *
0x180023f93  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180023f9a  mov     edx, 18Dh; void *
0x180023f9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023fa4  nop
0x180023fa5  mov     rcx, [rbp+57h+var_B8]
0x180023fa9  mov     [rbp+57h+var_B8], 0
0x180023fb1  test    rcx, rcx
0x180023fb4  jz      short loc_180023FC3
0x180023fb6  mov     rax, [rcx]
0x180023fb9  mov     rax, [rax+10h]
0x180023fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fc2  nop
0x180023fc3  lea     rax, [rbp+57h+var_B8]
0x180023fc7  mov     qword ptr [rsp+0F0h+ppv], rax; ppv
0x180023fcc  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180023fd3  xor     edx, edx; pUnkOuter
0x180023fd5  lea     r8d, [rdx+1]; dwClsContext
0x180023fd9  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180023fe0  call    cs:__imp_CoCreateInstance
0x180023fe7  nop     dword ptr [rax+rax+00h]
0x180023fec  mov     ebx, eax
0x180023fee  test    eax, eax
0x180023ff0  jns     short loc_180023FFC
0x180023ff2  mov     edx, 195h
0x180023ff7  jmp     loc_180023F1D
0x180023ffc  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x180024001  mov     rax, [rbp+57h+var_B8]
0x180024005  mov     [rbp+57h+var_B8], 0
0x18002400d  mov     [rsi], rax
0x180024010  lea     rcx, [rbp+57h+var_98]
0x180024014  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180024019  xor     ebx, ebx
0x18002401b  lea     rcx, [rbp+57h+var_B8]
0x18002401f  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180024024  mov     eax, ebx
0x180024026  mov     rcx, [rbp+57h+var_20]
0x18002402a  xor     rcx, rsp; StackCookie
0x18002402d  call    __security_check_cookie
0x180024032  mov     rbx, [rsp+0F0h+arg_18]
0x18002403a  add     rsp, 0E0h
0x180024041  pop     rdi
0x180024042  pop     rsi
0x180024043  pop     rbp
0x180024044  retn
0x180024046  mov     rcx, [rbp+57h+var_B8]
0x18002404a  mov     [rbp+57h+var_B8], 0
0x180024052  test    rcx, rcx
0x180024055  jz      short loc_180024064
0x180024057  mov     rax, [rcx]
0x18002405a  mov     rax, [rax+10h]
0x18002405e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024063  nop
0x180024064  lea     rax, [rbp+57h+var_B8]
0x180024068  mov     qword ptr [rsp+0F0h+ppv], rax; ppv
0x18002406d  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180024074  xor     edx, edx; pUnkOuter
0x180024076  lea     r8d, [rdx+1]; dwClsContext
0x18002407a  lea     rcx, _GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317; rclsid
0x180024081  call    cs:__imp_CoCreateInstance
0x180024088  nop     dword ptr [rax+rax+00h]
0x18002408d  mov     ebx, eax
0x18002408f  test    eax, eax
0x180024091  jns     loc_180024001
0x180024097  mov     edx, 1A3h
0x18002409c  jmp     loc_180023F1D
```
