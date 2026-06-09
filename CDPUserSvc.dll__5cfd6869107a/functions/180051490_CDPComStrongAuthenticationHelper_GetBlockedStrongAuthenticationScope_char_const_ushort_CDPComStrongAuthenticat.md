# CDPComStrongAuthenticationHelper::GetBlockedStrongAuthenticationScope(char const *,ushort *,CDPComStrongAuthenticationScope * *)

- ea: `0x180051490`
- end: `0x180051827`
- name: `?GetBlockedStrongAuthenticationScope@CDPComStrongAuthenticationHelper@@UEAAJPEBDPEAGPEAPEAUCDPComStrongAuthenticationScope@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(CDPComStrongAuthenticationHelper *__hidden this, const char *, unsigned __int16 *, struct CDPComStrongAuthenticationScope **)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004a58`
- `0x18000ecb8`
- `0x18001d0f4`
- `0x180020cc4`
- `0x18002c570`
- `0x180051114`
- `0x1800511dc`
- `0x180051298`
- `0x1800512ac`
- `0x1800512bc`
- `0x180051490`
- `0x180051bdc`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005159d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005159d`

## string_xrefs

- `0x1800514dd`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x180051516`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x1800515e0`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x1800516d6`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CDPComStrongAuthenticationHelper::GetBlockedStrongAuthenticationScope(
        CDPComStrongAuthenticationHelper *this,
        const char *a2,
        unsigned __int16 *a3,
        struct CDPComStrongAuthenticationScope **a4)
{
  __int64 v7; // rbx
  void (__fastcall *v8)(__int64, char **, _QWORD *); // rdi
  char *v9; // rdi
  char *v10; // rbx
  unsigned __int64 v11; // rax
  unsigned int v12; // ebx
  LPVOID v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  char *v17; // rdi
  __int64 *v18; // rax
  __int64 v19; // r15
  _WORD *v20; // r14
  unsigned __int16 v21; // ax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // edi
  LPVOID *v26; // rbx
  char *v27; // rbx
  char *v28; // rdi
  unsigned int v29; // [rsp+30h] [rbp-A8h] BYREF
  int v30; // [rsp+34h] [rbp-A4h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-A0h] BYREF
  char *v32; // [rsp+40h] [rbp-98h] BYREF
  char *v33; // [rsp+48h] [rbp-90h]
  __int64 v34; // [rsp+50h] [rbp-88h]
  _QWORD v35[2]; // [rsp+58h] [rbp-80h] BYREF
  char v36[16]; // [rsp+68h] [rbp-70h] BYREF
  _QWORD v37[2]; // [rsp+78h] [rbp-60h] BYREF
  char v38; // [rsp+88h] [rbp-50h]

  if ( a2 )
  {
    if ( a3 )
    {
      v7 = *((_QWORD *)this + 3);
      v8 = *(void (__fastcall **)(__int64, char **, _QWORD *))(*(_QWORD *)v7 + 24LL);
      std::string::string((__int64)v37, (__int64)a2);
      v8(v7, &v32, v37);
      std::string::_Tidy_deallocate(v37);
      v9 = v33;
      v10 = v32;
      v11 = 0xCCCCCCCCCCCCCCCDuLL * ((v33 - v32) >> 3);
      *a3 = v11;
      if ( (_WORD)v11 )
      {
        v12 = (unsigned __int16)v11;
        v13 = CoTaskMemAlloc(16LL * (unsigned __int16)v11);
        wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
          v35,
          v13,
          v12);
        if ( (unsigned __int8)wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator bool(v35) )
        {
          LOWORD(v31) = 0;
          v18 = (__int64 *)wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
                             v36,
                             v35,
                             &v31);
          v19 = *v18;
          v37[0] = *v18;
          v20 = (_WORD *)v18[1];
          v37[1] = v20;
          v38 = 1;
          v21 = v31;
          while ( 1 )
          {
            if ( v21 >= *a3 )
            {
              *a4 = (struct CDPComStrongAuthenticationScope *)wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(v35);
              wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v35);
              v9 = v33;
              v10 = v32;
              goto LABEL_26;
            }
            v22 = CDPStrongAuthenticationScopeToComStrongAuthenticationScope(&v32[40 * v21], v35[0] + 16LL * v21);
            if ( v22 < 0 )
              break;
            v21 = v31 + 1;
            LOWORD(v31) = v31 + 1;
          }
          v29 = v22;
          v30 = 100;
          Log<long &,char const (&)[40],int>(v24, v23, &v29, "..\\cdpcomstrongauthenticationhelper.cpp", &v30);
          v25 = 0;
          if ( *v20 )
          {
            do
            {
              v26 = (LPVOID *)wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                                v19,
                                v25);
              CoTaskMemFree(*v26);
              *v26 = 0;
              ++v25;
            }
            while ( v25 < (unsigned __int16)*v20 );
          }
          wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v35);
          v27 = v32;
          if ( v32 )
          {
            v28 = v33;
            if ( v32 != v33 )
            {
              do
              {
                std::string::_Tidy_deallocate(v27);
                v27 += 40;
              }
              while ( v27 != v28 );
              v27 = v32;
            }
            std::_Deallocate<16>(v27, 8 * ((v34 - (__int64)v27) >> 3));
          }
          return v29;
        }
        else
        {
          v29 = -2147024882;
          v30 = 86;
          Log<long &,char const (&)[40],int>(v15, v14, &v29, "..\\cdpcomstrongauthenticationhelper.cpp", &v30);
          wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v35);
          v16 = v32;
          if ( v32 )
          {
            v17 = v33;
            if ( v32 != v33 )
            {
              do
              {
                std::string::_Tidy_deallocate(v16);
                v16 += 40;
              }
              while ( v16 != v17 );
              v16 = v32;
            }
            std::_Deallocate<16>(v16, 8 * ((v34 - (__int64)v16) >> 3));
          }
          return v29;
        }
      }
      else
      {
LABEL_26:
        if ( v10 )
        {
          if ( v10 != v9 )
          {
            do
            {
              std::string::_Tidy_deallocate(v10);
              v10 += 40;
            }
            while ( v10 != v9 );
            v10 = v32;
          }
          std::_Deallocate<16>(v10, 8 * ((v34 - (__int64)v10) >> 3));
        }
        return 0;
      }
    }
    else
    {
      v31 = -2147024809;
      v29 = 75;
      Log<long &,char const (&)[40],int>(
        (__int64)this,
        (__int64)a2,
        &v31,
        "..\\cdpcomstrongauthenticationhelper.cpp",
        &v29);
      return v31;
    }
  }
  else
  {
    v31 = -2147024809;
    v29 = 74;
    Log<long &,char const (&)[40],int>((__int64)this, 0, &v31, "..\\cdpcomstrongauthenticationhelper.cpp", &v29);
    return v31;
  }
}

```

## disassembly

```asm
0x180051490  push    rbx
0x180051492  push    rsi
0x180051493  push    rdi
0x180051494  push    r12
0x180051496  push    r13
0x180051498  push    r14
0x18005149a  push    r15
0x18005149c  sub     rsp, 0A0h
0x1800514a3  mov     rax, cs:__security_cookie
0x1800514aa  xor     rax, rsp
0x1800514ad  mov     [rsp+0D8h+var_40], rax
0x1800514b5  mov     r12, r9
0x1800514b8  mov     rsi, r8
0x1800514bb  xor     r13d, r13d
0x1800514be  test    rdx, rdx
0x1800514c1  jnz     short loc_1800514F7
0x1800514c3  mov     [rsp+0D8h+var_A0], 80070057h
0x1800514cb  mov     [rsp+0D8h+var_A8], 4Ah ; 'J'
0x1800514d3  lea     rax, [rsp+0D8h+var_A8]
0x1800514d8  mov     [rsp+0D8h+var_B8], rax
0x1800514dd  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800514e4  lea     r8, [rsp+0D8h+var_A0]
0x1800514e9  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800514ee  mov     eax, [rsp+0D8h+var_A0]
0x1800514f2  jmp     loc_180051803
0x1800514f7  test    rsi, rsi
0x1800514fa  jnz     short loc_180051530
0x1800514fc  mov     [rsp+0D8h+var_A0], 80070057h
0x180051504  mov     [rsp+0D8h+var_A8], 4Bh ; 'K'
0x18005150c  lea     rax, [rsp+0D8h+var_A8]
0x180051511  mov     [rsp+0D8h+var_B8], rax
0x180051516  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x18005151d  lea     r8, [rsp+0D8h+var_A0]
0x180051522  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180051527  mov     eax, [rsp+0D8h+var_A0]
0x18005152b  jmp     loc_180051803
0x180051530  mov     rbx, [rcx+18h]
0x180051534  mov     rax, [rbx]
0x180051537  mov     rdi, [rax+18h]
0x18005153b  lea     rcx, [rsp+0D8h+var_60]
0x180051540  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051545  nop
0x180051546  lea     r8, [rsp+0D8h+var_60]
0x18005154b  lea     rdx, [rsp+0D8h+var_98]
0x180051550  mov     rcx, rbx
0x180051553  mov     rax, rdi
0x180051556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005155b  nop
0x18005155c  lea     rcx, [rsp+0D8h+var_60]
0x180051561  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180051566  mov     rdi, [rsp+0D8h+var_90]
0x18005156b  mov     rax, rdi
0x18005156e  mov     rbx, [rsp+0D8h+var_98]
0x180051573  sub     rax, rbx
0x180051576  sar     rax, 3
0x18005157a  mov     r14, 0CCCCCCCCCCCCCCCDh
0x180051584  imul    rax, r14
0x180051588  mov     [rsi], ax
0x18005158b  test    ax, ax
0x18005158e  jz      loc_1800517BB
0x180051594  movzx   ebx, ax
0x180051597  mov     ecx, ebx
0x180051599  shl     rcx, 4; cb
0x18005159d  call    cs:__imp_CoTaskMemAlloc
0x1800515a3  mov     r8d, ebx
0x1800515a6  mov     rdx, rax
0x1800515a9  lea     rcx, [rsp+0D8h+var_80]
0x1800515ae  call    ??0?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@PEAUCDPComStrongAuthenticationScope@@_K@Z; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(CDPComStrongAuthenticationScope *,unsigned __int64)
0x1800515b3  nop
0x1800515b4  lea     rcx, [rsp+0D8h+var_80]
0x1800515b9  call    ??B?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEBA_NXZ; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator bool(void)
0x1800515be  test    al, al
0x1800515c0  jnz     loc_180051650
0x1800515c6  mov     [rsp+0D8h+var_A8], 8007000Eh
0x1800515ce  mov     [rsp+0D8h+var_A4], 56h ; 'V'
0x1800515d6  lea     rax, [rsp+0D8h+var_A4]
0x1800515db  mov     [rsp+0D8h+var_B8], rax
0x1800515e0  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800515e7  lea     r8, [rsp+0D8h+var_A8]
0x1800515ec  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800515f1  nop
0x1800515f2  lea     rcx, [rsp+0D8h+var_80]
0x1800515f7  call    ??1?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x1800515fc  nop
0x1800515fd  mov     rbx, [rsp+0D8h+var_98]
0x180051602  test    rbx, rbx
0x180051605  jz      short loc_180051647
0x180051607  mov     rdi, [rsp+0D8h+var_90]
0x18005160c  cmp     rbx, rdi
0x18005160f  jz      short loc_180051627
0x180051611  mov     rcx, rbx
0x180051614  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180051619  add     rbx, 28h ; '('
0x18005161d  cmp     rbx, rdi
0x180051620  jnz     short loc_180051611
0x180051622  mov     rbx, [rsp+0D8h+var_98]
0x180051627  mov     rdx, [rsp+0D8h+var_88]
0x18005162c  sub     rdx, rbx
0x18005162f  sar     rdx, 3
0x180051633  imul    rdx, r14
0x180051637  lea     rdx, [rdx+rdx*4]
0x18005163b  shl     rdx, 3
0x18005163f  mov     rcx, rbx
0x180051642  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180051647  mov     eax, [rsp+0D8h+var_A8]
0x18005164b  jmp     loc_180051803
0x180051650  mov     word ptr [rsp+0D8h+var_A0], r13w
0x180051656  lea     r8, [rsp+0D8h+var_A0]
0x18005165b  lea     rdx, [rsp+0D8h+var_80]
0x180051660  lea     rcx, [rsp+0D8h+var_70]
0x180051665  call    ??0?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@PEAUCDPComStrongAuthenticationScope@@_K@Z; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(CDPComStrongAuthenticationScope *,unsigned __int64)
0x18005166a  mov     r15, [rax]
0x18005166d  mov     [rsp+0D8h+var_60], r15
0x180051672  mov     r14, [rax+8]
0x180051676  mov     [rsp+0D8h+var_58], r14
0x18005167e  mov     ebx, 1
0x180051683  mov     [rsp+0D8h+var_50], bl
0x18005168a  movzx   eax, word ptr [rsp+0D8h+var_A0]
0x18005168f  cmp     ax, [rsi]
0x180051692  jnb     loc_18005178F
0x180051698  movzx   eax, ax
0x18005169b  mov     edx, eax
0x18005169d  shl     rdx, 4
0x1800516a1  add     rdx, [rsp+0D8h+var_80]
0x1800516a6  lea     rcx, [rax+rax*4]
0x1800516aa  mov     rax, [rsp+0D8h+var_98]
0x1800516af  lea     rcx, [rax+rcx*8]
0x1800516b3  call    CDPStrongAuthenticationScopeToComStrongAuthenticationScope
0x1800516b8  test    eax, eax
0x1800516ba  jns     loc_18005177D
0x1800516c0  mov     [rsp+0D8h+var_A8], eax
0x1800516c4  mov     [rsp+0D8h+var_A4], 64h ; 'd'
0x1800516cc  lea     rax, [rsp+0D8h+var_A4]
0x1800516d1  mov     [rsp+0D8h+var_B8], rax
0x1800516d6  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800516dd  lea     r8, [rsp+0D8h+var_A8]
0x1800516e2  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800516e7  nop
0x1800516e8  mov     edi, r13d
0x1800516eb  cmp     r13w, [r14]
0x1800516ef  jnb     short loc_180051715
0x1800516f1  movsxd  rdx, edi
0x1800516f4  mov     rcx, r15
0x1800516f7  call    ??A?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAAEAUCDPComStrongAuthenticationScope@@_K@Z; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x1800516fc  mov     rbx, rax
0x1800516ff  mov     rcx, [rax]; pv
0x180051702  call    cs:__imp_CoTaskMemFree
0x180051708  mov     [rbx], r13
0x18005170b  inc     edi
0x18005170d  movzx   eax, word ptr [r14]
0x180051711  cmp     edi, eax
0x180051713  jl      short loc_1800516F1
0x180051715  lea     rcx, [rsp+0D8h+var_80]
0x18005171a  call    ??1?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18005171f  nop
0x180051720  mov     rbx, [rsp+0D8h+var_98]
0x180051725  test    rbx, rbx
0x180051728  jz      short loc_180051774
0x18005172a  mov     rdi, [rsp+0D8h+var_90]
0x18005172f  cmp     rbx, rdi
0x180051732  jz      short loc_18005174A
0x180051734  mov     rcx, rbx
0x180051737  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005173c  add     rbx, 28h ; '('
0x180051740  cmp     rbx, rdi
0x180051743  jnz     short loc_180051734
0x180051745  mov     rbx, [rsp+0D8h+var_98]
0x18005174a  mov     rdx, [rsp+0D8h+var_88]
0x18005174f  sub     rdx, rbx
0x180051752  sar     rdx, 3
0x180051756  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180051760  imul    rdx, rax
0x180051764  lea     rdx, [rdx+rdx*4]
0x180051768  shl     rdx, 3
0x18005176c  mov     rcx, rbx
0x18005176f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180051774  mov     eax, [rsp+0D8h+var_A8]
0x180051778  jmp     loc_180051803
0x18005177d  movzx   eax, word ptr [rsp+0D8h+var_A0]
0x180051782  add     ax, bx
0x180051785  mov     word ptr [rsp+0D8h+var_A0], ax
0x18005178a  jmp     loc_18005168F
0x18005178f  lea     rcx, [rsp+0D8h+var_80]
0x180051794  call    ?release@?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAUCDPComStrongAuthenticationScope@@XZ; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(void)
0x180051799  mov     [r12], rax
0x18005179d  lea     rcx, [rsp+0D8h+var_80]
0x1800517a2  call    ??1?$unique_any_array_ptr@UCDPComStrongAuthenticationScope@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<CDPComStrongAuthenticationScope,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x1800517a7  mov     rdi, [rsp+0D8h+var_90]
0x1800517ac  mov     rbx, [rsp+0D8h+var_98]
0x1800517b1  mov     r14, 0CCCCCCCCCCCCCCCDh
0x1800517bb  test    rbx, rbx
0x1800517be  jz      short loc_1800517FB
0x1800517c0  cmp     rbx, rdi
0x1800517c3  jz      short loc_1800517DB
0x1800517c5  mov     rcx, rbx
0x1800517c8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800517cd  add     rbx, 28h ; '('
0x1800517d1  cmp     rbx, rdi
0x1800517d4  jnz     short loc_1800517C5
0x1800517d6  mov     rbx, [rsp+0D8h+var_98]
0x1800517db  mov     rax, [rsp+0D8h+var_88]
0x1800517e0  sub     rax, rbx
0x1800517e3  sar     rax, 3
0x1800517e7  imul    rax, r14
0x1800517eb  lea     rdx, [rax+rax*4]
0x1800517ef  shl     rdx, 3
0x1800517f3  mov     rcx, rbx
0x1800517f6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800517fb  xor     eax, eax
0x1800517fd  jmp     short loc_180051803
0x1800517ff  mov     eax, [rsp+0D8h+var_A4]
0x180051803  mov     rcx, [rsp+0D8h+var_40]
0x18005180b  xor     rcx, rsp; StackCookie
0x18005180e  call    __security_check_cookie
0x180051813  add     rsp, 0A0h
0x18005181a  pop     r15
0x18005181c  pop     r14
0x18005181e  pop     r13
0x180051820  pop     r12
0x180051822  pop     rdi
0x180051823  pop     rsi
0x180051824  pop     rbx
0x180051825  retn
```
