# CDPComSettingsInterop::GetCurrentMachineDeviceId(char * *)

- ea: `0x180006290`
- end: `0x180006400`
- name: `?GetCurrentMachineDeviceId@CDPComSettingsInterop@@UEAAJPEAPEAD@Z`
- size: `368`
- prototype: `__int64 __fastcall(CDPComSettingsInterop *__hidden this, char **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006290`
- `0x18001a5b4`
- `0x18001ddf8`
- `0x1800225a0`
- `0x180034f60`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800063d8`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800063d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800063ef`

## string_xrefs

- `0x180006320`: `.\cdpcomsettingsinterop.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDPComSettingsInterop::GetCurrentMachineDeviceId(CDPComSettingsInterop *this, char **a2)
{
  int v4; // esi
  __int64 result; // rax
  char **v6; // rdx
  char *v7; // rax
  char *v8; // rbx
  const char *v9; // r8
  SIZE_T v10; // rax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+34h] [rbp-44h] BYREF
  SIZE_T cb; // [rsp+38h] [rbp-40h] BYREF
  char *Source[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v17; // [rsp+50h] [rbp-28h]

  try
  {
    if ( a2 )
    {
      *a2 = 0;
      LODWORD(cb) = 0;
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, SIZE_T *))(**((_QWORD **)this + 3) + 24LL))(
             *((_QWORD *)this + 3),
             0,
             &cb) == -2147221235 )
      {
        *(_OWORD *)Source = 0;
        v17 = 0;
        std::string::_Construct<0,char>(Source, 0, (unsigned int)cb);
        v6 = Source;
        if ( *((_QWORD *)&v17 + 1) > 0xFu )
          v6 = (char **)Source[0];
        v4 = (*(__int64 (__fastcall **)(_QWORD, char **, SIZE_T *))(**((_QWORD **)this + 3) + 24LL))(
               *((_QWORD *)this + 3),
               v6,
               &cb);
        if ( v4 >= 0 )
        {
          v7 = (char *)CoTaskMemAlloc((unsigned int)cb);
          v8 = v7;
          if ( v7 )
          {
            v9 = (const char *)Source;
            if ( *((_QWORD *)&v17 + 1) > 0xFu )
              v9 = Source[0];
            if ( strcpy_s(v7, (unsigned int)cb, v9) )
            {
              v4 = -2147024809;
              CoTaskMemFree(v8);
            }
            else
            {
              *a2 = v8;
            }
          }
          else
          {
            v4 = -2147024882;
          }
        }
        if ( *((_QWORD *)&v17 + 1) > 0xFu )
          std::_Deallocate<16>(Source[0], *((_QWORD *)&v17 + 1) + 1LL);
      }
      else
      {
        v4 = -2147418113;
      }
      result = (unsigned int)v4;
    }
    else
    {
      v13 = -2147467261;
      v14 = 27;
      Log<long &,char const (&)[28],int>(
        (_DWORD)this,
        0,
        (unsigned int)&v13,
        (unsigned int)".\\cdpcomsettingsinterop.cpp",
        (__int64)&v14);
      result = v13;
    }
  }
  catch ( ... )
  {
    v13 = -2147418113;
    LODWORD(v10) = GetCurrentThreadId();
    cb = v10;
    v14 = 71;
    cdp::CatchAllToHR<char const (&)[28],int,unsigned __int64>(
      (unsigned int)&v13,
      v11,
      v12,
      (unsigned int)&v14,
      (__int64)&cb);
  }
  return result;
}

```

## disassembly

```asm
0x180006290  mov     [rsp+arg_10], rbx
0x180006295  mov     [rsp+arg_18], rsi
0x18000629a  push    rdi
0x18000629b  sub     rsp, 70h
0x18000629f  mov     rax, cs:__security_cookie
0x1800062a6  xor     rax, rsp
0x1800062a9  mov     [rsp+78h+var_18], rax
0x1800062ae  mov     rdi, rdx
0x1800062b1  mov     rbx, rcx
0x1800062b4  test    rdx, rdx
0x1800062b7  jz      short loc_180006306
0x1800062b9  xor     eax, eax
0x1800062bb  mov     [rdx], rax
0x1800062be  mov     dword ptr [rsp+78h+cb], eax
0x1800062c2  mov     rcx, [rcx+18h]
0x1800062c6  mov     rax, [rcx]
0x1800062c9  lea     r8, [rsp+78h+cb]
0x1800062ce  xor     edx, edx
0x1800062d0  mov     rax, [rax+18h]
0x1800062d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d9  cmp     eax, 8004010Dh
0x1800062de  jz      short loc_180006337
0x1800062e0  mov     esi, 8000FFFFh
0x1800062e5  mov     eax, esi
0x1800062e7  mov     rcx, [rsp+78h+var_18]
0x1800062ec  xor     rcx, rsp; StackCookie
0x1800062ef  call    __security_check_cookie
0x1800062f4  lea     r11, [rsp+78h+var_8]
0x1800062f9  mov     rbx, [r11+20h]
0x1800062fd  mov     rsi, [r11+28h]
0x180006301  mov     rsp, r11
0x180006304  pop     rdi
0x180006305  retn
0x180006306  mov     [rsp+78h+var_48], 80004003h
0x18000630e  mov     [rsp+78h+var_44], 1Bh
0x180006316  lea     rax, [rsp+78h+var_44]
0x18000631b  mov     [rsp+78h+var_58], rax
0x180006320  lea     r9, aCdpcomsettings; ".\\cdpcomsettingsinterop.cpp"
0x180006327  lea     r8, [rsp+78h+var_48]
0x18000632c  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180006331  mov     eax, [rsp+78h+var_48]
0x180006335  jmp     short loc_1800062E7
0x180006337  xorps   xmm0, xmm0
0x18000633a  movups  xmmword ptr [rsp+78h+Source], xmm0
0x18000633f  xorps   xmm1, xmm1
0x180006342  movdqu  [rsp+78h+var_28], xmm1
0x180006348  mov     r8d, dword ptr [rsp+78h+cb]
0x18000634d  xor     edx, edx
0x18000634f  lea     rcx, [rsp+78h+Source]
0x180006354  call    ??$_Construct@$0A@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXD_K@Z; std::string::_Construct<0,char>(char,unsigned __int64)
0x180006359  nop
0x18000635a  mov     rcx, [rbx+18h]
0x18000635e  mov     rax, [rcx]
0x180006361  lea     rdx, [rsp+78h+Source]
0x180006366  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x18000636c  cmova   rdx, [rsp+78h+Source]
0x180006372  lea     r8, [rsp+78h+cb]
0x180006377  mov     rax, [rax+18h]
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  mov     esi, eax
0x180006382  test    eax, eax
0x180006384  jns     short loc_1800063A7
0x180006386  mov     rdx, qword ptr [rsp+78h+var_28+8]
0x18000638b  cmp     rdx, 0Fh
0x18000638f  jbe     loc_1800062E5
0x180006395  inc     rdx
0x180006398  mov     rcx, [rsp+78h+Source]
0x18000639d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800063a2  jmp     loc_1800062E5
0x1800063a7  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x1800063ab  call    cs:__imp_CoTaskMemAlloc
0x1800063b1  mov     rbx, rax
0x1800063b4  test    rax, rax
0x1800063b7  jnz     short loc_1800063C0
0x1800063b9  mov     esi, 8007000Eh
0x1800063be  jmp     short loc_180006386
0x1800063c0  lea     r8, [rsp+78h+Source]
0x1800063c5  cmp     qword ptr [rsp+78h+var_28+8], 0Fh
0x1800063cb  cmova   r8, [rsp+78h+Source]; Source
0x1800063d1  mov     edx, dword ptr [rsp+78h+cb]; SizeInBytes
0x1800063d5  mov     rcx, rbx; Destination
0x1800063d8  call    cs:__imp_strcpy_s
0x1800063de  test    eax, eax
0x1800063e0  jnz     short loc_1800063E7
0x1800063e2  mov     [rdi], rbx
0x1800063e5  jmp     short loc_180006386
0x1800063e7  mov     esi, 80070057h
0x1800063ec  mov     rcx, rbx; pv
0x1800063ef  call    cs:__imp_CoTaskMemFree
0x1800063f5  jmp     short loc_180006386
0x1800063f7  mov     eax, [rsp+78h+var_44]
0x1800063fb  jmp     loc_1800062E7
```
