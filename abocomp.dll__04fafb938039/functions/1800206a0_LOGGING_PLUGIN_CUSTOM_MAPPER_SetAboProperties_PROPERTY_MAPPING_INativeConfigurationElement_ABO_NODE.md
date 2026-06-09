# LOGGING_PLUGIN_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x1800206a0`
- end: `0x180020881`
- name: `?SetAboProperties@LOGGING_PLUGIN_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `481`
- prototype: `int(LOGGING_PLUGIN_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000a838`
- `0x1800206a0`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800207a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800207a8`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180020806`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180020806`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020702`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020702`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020857`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020857`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800207f6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800207f6`

## string_xrefs

- `0x18002076d`: `customLogPluginClsid`

## pseudocode

```c
__int64 __fastcall LOGGING_PLUGIN_CUSTOM_MAPPER::SetAboProperties(
        LOGGING_PLUGIN_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  const unsigned __int16 *v7; // rdx
  int v8; // ebx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _METADATA_RECORD v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[56]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v14[256]; // [rsp+A0h] [rbp-60h] BYREF

  v10 = 0;
  v11 = 0;
  memset_0(v14, 0, sizeof(v14));
  STRU::STRU((STRU *)v13, v14, 0x100u);
  if ( a2 && a3 && a4 )
  {
    if ( (*(unsigned int (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a3 + 48LL))(
           a3,
           L"logFormat",
           &v10,
           0,
           0) == -2147024894 )
      v10 = 2;
    (*(void (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)a3 + 64LL))(
      a3,
      L"customLogPluginClsid",
      &v11,
      0,
      0);
    if ( v10 )
    {
      if ( v10 == 1 )
      {
        v7 = NCSA_LOG_FORMAT_ID;
      }
      else if ( v10 == 2 )
      {
        v7 = W3C_LOG_FORMAT_ID;
      }
      else
      {
        v7 = v11;
      }
    }
    else
    {
      v7 = IIS_LOG_FORMAT_ID;
    }
    v8 = STRU::Copy((STRU *)v13, v7);
    if ( v8 >= 0 )
    {
      v12.dwMDIdentifier = *((_DWORD *)a2 + 36);
      v12.dwMDUserType = *((_DWORD *)a2 + 37);
      v12.dwMDDataType = *((_DWORD *)a2 + 38);
      v12.dwMDAttributes = *((_DWORD *)a2 + 39);
      *(&v12.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v12.dwMDDataTag = 0;
      v12.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v13);
      v12.dwMDDataLen = STRU::QueryCB((STRU *)v13) + 2;
      v8 = ABO_NODE::SetDataByMapping(a4, &v12, a2);
    }
  }
  else
  {
    v8 = -2147024809;
  }
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800206a0  mov     [rsp-8+arg_0], rbx
0x1800206a5  push    rbp
0x1800206a6  push    rsi
0x1800206a7  push    rdi
0x1800206a8  lea     rbp, [rsp-1B0h]
0x1800206b0  sub     rsp, 2B0h
0x1800206b7  mov     rax, cs:__security_cookie
0x1800206be  xor     rax, rsp
0x1800206c1  mov     [rbp+1C0h+var_20], rax
0x1800206c8  mov     rbx, r8
0x1800206cb  mov     [rsp+2C0h+var_290], 0
0x1800206d3  mov     rdi, rdx
0x1800206d6  mov     [rsp+2C0h+var_288], 0
0x1800206df  xor     edx, edx; Val
0x1800206e1  lea     rcx, [rbp+1C0h+var_220]; void *
0x1800206e5  mov     r8d, 200h; Size
0x1800206eb  mov     rsi, r9
0x1800206ee  call    memset_0
0x1800206f3  mov     r8d, 100h
0x1800206f9  lea     rdx, [rbp+1C0h+var_220]
0x1800206fd  lea     rcx, [rsp+2C0h+var_258]
0x180020702  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180020708  test    rdi, rdi
0x18002070b  jz      loc_18002084D
0x180020711  test    rbx, rbx
0x180020714  jz      loc_18002084D
0x18002071a  test    rsi, rsi
0x18002071d  jz      loc_18002084D
0x180020723  mov     rax, [rbx]
0x180020726  lea     r8, [rsp+2C0h+var_290]
0x18002072b  xor     r9d, r9d
0x18002072e  mov     [rsp+2C0h+var_2A0], 0
0x180020737  lea     rdx, aLogformat; "logFormat"
0x18002073e  mov     rcx, rbx
0x180020741  mov     rax, [rax+30h]
0x180020745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002074a  cmp     eax, 80070002h
0x18002074f  jnz     short loc_180020759
0x180020751  mov     [rsp+2C0h+var_290], 2
0x180020759  mov     rax, [rbx]
0x18002075c  lea     r8, [rsp+2C0h+var_288]
0x180020761  xor     r9d, r9d
0x180020764  mov     [rsp+2C0h+var_2A0], 0
0x18002076d  lea     rdx, aCustomlogplugi; "customLogPluginClsid"
0x180020774  mov     rcx, rbx
0x180020777  mov     rax, [rax+40h]
0x18002077b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020780  mov     eax, [rsp+2C0h+var_290]
0x180020784  test    eax, eax
0x180020786  jz      loc_18002083C
0x18002078c  sub     eax, 1
0x18002078f  jz      loc_180020833
0x180020795  lea     rcx, [rsp+2C0h+var_258]
0x18002079a  cmp     eax, 1
0x18002079d  jz      loc_180020827
0x1800207a3  mov     rdx, [rsp+2C0h+var_288]
0x1800207a8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800207ae  mov     ebx, eax
0x1800207b0  test    eax, eax
0x1800207b2  js      loc_180020852
0x1800207b8  mov     eax, [rdi+90h]
0x1800207be  lea     rcx, [rsp+2C0h+var_258]
0x1800207c3  mov     [rsp+2C0h+var_280.dwMDIdentifier], eax
0x1800207c7  mov     eax, [rdi+94h]
0x1800207cd  mov     [rsp+2C0h+var_280.dwMDUserType], eax
0x1800207d1  mov     eax, [rdi+98h]
0x1800207d7  mov     [rsp+2C0h+var_280.dwMDDataType], eax
0x1800207db  mov     eax, [rdi+9Ch]
0x1800207e1  mov     [rsp+2C0h+var_280.dwMDAttributes], eax
0x1800207e5  mov     dword ptr [rsp+2C0h+var_280+14h], 0
0x1800207ed  mov     qword ptr [rsp+2C0h+var_280.dwMDDataTag], 0
0x1800207f6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800207fc  lea     rcx, [rsp+2C0h+var_258]
0x180020801  mov     [rsp+2C0h+var_280.pbMDData], rax
0x180020806  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18002080c  mov     r8, rdi; struct PROPERTY_MAPPING *
0x18002080f  lea     rdx, [rsp+2C0h+var_280]; struct _METADATA_RECORD *
0x180020814  add     eax, 2
0x180020817  mov     rcx, rsi; this
0x18002081a  mov     [rsp+2C0h+var_280.dwMDDataLen], eax
0x18002081e  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x180020823  mov     ebx, eax
0x180020825  jmp     short loc_180020852
0x180020827  lea     rdx, ?W3C_LOG_FORMAT_ID@@3PAGA; "{FF160663-DE82-11CF-BC0A-00AA006111E0}"
0x18002082e  jmp     loc_1800207A8
0x180020833  lea     rdx, ?NCSA_LOG_FORMAT_ID@@3PAGA; "{FF16065F-DE82-11CF-BC0A-00AA006111E0}"
0x18002083a  jmp     short loc_180020843
0x18002083c  lea     rdx, ?IIS_LOG_FORMAT_ID@@3PAGA; "{FF160657-DE82-11CF-BC0A-00AA006111E0}"
0x180020843  lea     rcx, [rsp+2C0h+var_258]
0x180020848  jmp     loc_1800207A8
0x18002084d  mov     ebx, 80070057h
0x180020852  lea     rcx, [rsp+2C0h+var_258]
0x180020857  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002085d  mov     eax, ebx
0x18002085f  mov     rcx, [rbp+1C0h+var_20]
0x180020866  xor     rcx, rsp; StackCookie
0x180020869  call    __security_check_cookie
0x18002086e  mov     rbx, [rsp+2C0h+arg_0]
0x180020876  add     rsp, 2B0h
0x18002087d  pop     rdi
0x18002087e  pop     rsi
0x18002087f  pop     rbp
0x180020880  retn
```
