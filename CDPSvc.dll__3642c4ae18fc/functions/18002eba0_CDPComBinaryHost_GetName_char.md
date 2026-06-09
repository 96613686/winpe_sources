# CDPComBinaryHost::GetName(char * *)

- ea: `0x18002eba0`
- end: `0x18002ed77`
- name: `?GetName@CDPComBinaryHost@@UEAAJPEAPEAD@Z`
- size: `471`
- prototype: `__int64 __fastcall(CDPComBinaryHost *__hidden this, char **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006668`
- `0x18000c2e8`
- `0x18000c914`
- `0x18000cb8c`
- `0x18001f9f0`
- `0x1800225a0`
- `0x18002eba0`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002ecff`
- `msvcp_win!_Mtx_unlock` at `0x18002ed19`
- `msvcp_win!_Mtx_unlock` at `0x18002ed50`
- `msvcp_win!_Mtx_unlock` at `0x18002ecff`
- `msvcp_win!_Mtx_unlock` at `0x18002ed19`
- `msvcp_win!_Mtx_unlock` at `0x18002ed50`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18002ecb6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18002ecb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ec55`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComBinaryHost::GetName(CDPComBinaryHost *this, char **a2, __int64 a3, __int64 a4)
{
  struct _Mtx_internal_imp_t *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r9
  char *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // edi
  const char *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // [rsp+0h] [rbp-78h] BYREF
  unsigned int v25; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-44h] BYREF
  _Mtx_t v27; // [rsp+38h] [rbp-40h]
  char *v28; // [rsp+40h] [rbp-38h]
  char *Source[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v30; // [rsp+58h] [rbp-20h]
  unsigned __int64 v31; // [rsp+60h] [rbp-18h]

  if ( !a2 )
  {
    v25 = -2147467261;
    v26 = 105;
    Log<long &,char const (&)[23],int>((__int64)this, 0, &v25, a4, &v26);
    return v25;
  }
  v7 = (CDPComBinaryHost *)((char *)this + 32);
  v27 = (CDPComBinaryHost *)((char *)this + 32);
  v28 = (char *)this + 32;
  std::_Mutex_base::lock((CDPComBinaryHost *)((char *)this + 32));
  if ( !*((_QWORD *)this + 14) )
  {
    v25 = -2147221245;
    v26 = 109;
    Log<long &,char const (&)[23],int>(v9, v8, &v25, v10, &v26);
LABEL_15:
    v19 = v25;
    goto LABEL_16;
  }
  std::string::string(Source);
  try
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 24LL))(*((_QWORD *)this + 14));
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(v11 + v12) );
    std::string::_Assign<char>(Source);
  }
  catch ( ... )
  {
    v25 = -2147024882;
    v26 = 118;
    Log<long &,char const (&)[23],int>(v13, (__int64)&v24, &v25, v14, &v26);
    v26 = v25;
    std::string::~string(Source);
    _Mtx_unlock(v27);
    return v26;
  }
  v15 = (char *)CoTaskMemAlloc(v30 + 1);
  *a2 = v15;
  if ( v15 )
  {
    v20 = (const char *)Source;
    if ( v31 > 0xF )
      v20 = Source[0];
    if ( !strcpy_s(v15, v30 + 1, v20) )
    {
      std::string::~string(Source);
      _Mtx_unlock(v7);
      return 0;
    }
    v25 = -2147418113;
    v26 = 124;
    Log<long &,char const (&)[23],int>(v22, v21, &v25, v23, &v26);
    std::string::~string(Source);
    goto LABEL_15;
  }
  v25 = -2147024882;
  v26 = 122;
  Log<long &,char const (&)[23],int>(v17, v16, &v25, v18, &v26);
  v19 = v25;
  std::string::~string(Source);
LABEL_16:
  _Mtx_unlock(v7);
  return v19;
}

```

## disassembly

```asm
0x18002eba0  mov     r11, rsp
0x18002eba3  mov     [r11+18h], rbx
0x18002eba7  mov     [r11+20h], rsi
0x18002ebab  push    rdi
0x18002ebac  sub     rsp, 70h
0x18002ebb0  mov     rax, cs:__security_cookie
0x18002ebb7  xor     rax, rsp
0x18002ebba  mov     [rsp+78h+var_10], rax
0x18002ebbf  mov     rsi, rdx
0x18002ebc2  mov     rdi, rcx
0x18002ebc5  test    rdx, rdx
0x18002ebc8  jnz     short loc_18002EBF4
0x18002ebca  mov     [rsp+78h+var_48], 80004003h
0x18002ebd2  mov     [rsp+78h+var_44], 69h ; 'i'
0x18002ebda  lea     rax, [r11-44h]
0x18002ebde  mov     [r11-58h], rax
0x18002ebe2  lea     r8, [r11-48h]
0x18002ebe6  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18002ebeb  mov     eax, [rsp+78h+var_48]
0x18002ebef  jmp     loc_18002ED58
0x18002ebf4  lea     rbx, [rcx+20h]
0x18002ebf8  mov     [rsp+78h+var_40], rbx
0x18002ebfd  mov     [rsp+78h+var_38], rbx
0x18002ec02  mov     rcx, rbx; this
0x18002ec05  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002ec0a  nop
0x18002ec0b  cmp     qword ptr [rdi+70h], 0
0x18002ec10  jz      loc_18002ED25
0x18002ec16  lea     rcx, [rsp+78h+Source]
0x18002ec1b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18002ec20  nop
0x18002ec21  mov     rcx, [rdi+70h]
0x18002ec25  mov     rax, [rcx]
0x18002ec28  mov     rax, [rax+18h]
0x18002ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec31  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ec35  inc     r8
0x18002ec38  cmp     byte ptr [rax+r8], 0
0x18002ec3d  jnz     short loc_18002EC35
0x18002ec3f  mov     rdx, rax
0x18002ec42  lea     rcx, [rsp+78h+Source]
0x18002ec47  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18002ec4c  nop
0x18002ec4d  mov     rcx, [rsp+78h+var_20]
0x18002ec52  inc     rcx; cb
0x18002ec55  call    cs:__imp_CoTaskMemAlloc
0x18002ec5b  mov     [rsi], rax
0x18002ec5e  test    rax, rax
0x18002ec61  jnz     short loc_18002EC9A
0x18002ec63  mov     [rsp+78h+var_48], 8007000Eh
0x18002ec6b  mov     [rsp+78h+var_44], 7Ah ; 'z'
0x18002ec73  lea     rax, [rsp+78h+var_44]
0x18002ec78  mov     [rsp+78h+var_58], rax
0x18002ec7d  lea     r8, [rsp+78h+var_48]
0x18002ec82  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18002ec87  mov     edi, [rsp+78h+var_48]
0x18002ec8b  lea     rcx, [rsp+78h+Source]
0x18002ec90  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ec95  jmp     loc_18002ED4D
0x18002ec9a  lea     r8, [rsp+78h+Source]
0x18002ec9f  cmp     [rsp+78h+var_18], 0Fh
0x18002eca5  cmova   r8, [rsp+78h+Source]; Source
0x18002ecab  mov     rdx, [rsp+78h+var_20]
0x18002ecb0  inc     rdx; SizeInBytes
0x18002ecb3  mov     rcx, rax; Destination
0x18002ecb6  call    cs:__imp_strcpy_s
0x18002ecbc  test    eax, eax
0x18002ecbe  jz      short loc_18002ECF1
0x18002ecc0  mov     [rsp+78h+var_48], 8000FFFFh
0x18002ecc8  mov     [rsp+78h+var_44], 7Ch ; '|'
0x18002ecd0  lea     rax, [rsp+78h+var_44]
0x18002ecd5  mov     [rsp+78h+var_58], rax
0x18002ecda  lea     r8, [rsp+78h+var_48]
0x18002ecdf  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18002ece4  nop
0x18002ece5  lea     rcx, [rsp+78h+Source]
0x18002ecea  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ecef  jmp     short loc_18002ED49
0x18002ecf1  lea     rcx, [rsp+78h+Source]
0x18002ecf6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ecfb  nop
0x18002ecfc  mov     rcx, rbx; _Mtx_t
0x18002ecff  call    cs:__imp__Mtx_unlock
0x18002ed05  xor     eax, eax
0x18002ed07  jmp     short loc_18002ED58
0x18002ed09  lea     rcx, [rsp+78h+Source]
0x18002ed0e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002ed13  nop
0x18002ed14  mov     rcx, [rsp+78h+var_40]; _Mtx_t
0x18002ed19  call    cs:__imp__Mtx_unlock
0x18002ed1f  mov     eax, [rsp+78h+var_44]
0x18002ed23  jmp     short loc_18002ED58
0x18002ed25  mov     [rsp+78h+var_48], 80040103h
0x18002ed2d  mov     [rsp+78h+var_44], 6Dh ; 'm'
0x18002ed35  lea     rax, [rsp+78h+var_44]
0x18002ed3a  mov     [rsp+78h+var_58], rax
0x18002ed3f  lea     r8, [rsp+78h+var_48]
0x18002ed44  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18002ed49  mov     edi, [rsp+78h+var_48]
0x18002ed4d  mov     rcx, rbx; _Mtx_t
0x18002ed50  call    cs:__imp__Mtx_unlock
0x18002ed56  mov     eax, edi
0x18002ed58  mov     rcx, [rsp+78h+var_10]
0x18002ed5d  xor     rcx, rsp; StackCookie
0x18002ed60  call    __security_check_cookie
0x18002ed65  lea     r11, [rsp+78h+var_8]
0x18002ed6a  mov     rbx, [r11+20h]
0x18002ed6e  mov     rsi, [r11+28h]
0x18002ed72  mov     rsp, r11
0x18002ed75  pop     rdi
0x18002ed76  retn
```
