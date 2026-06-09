# Windows::Service::Task::AddWnfTriggerDelay(uchar const *,ulong,std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x18005b148`
- end: `0x18005b4f6`
- name: `?AddWnfTriggerDelay@Task@Service@Windows@@QEAAXPEBEKV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@Z`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18005c140`

## callees

- `0x180007660`
- `0x180018f7c`
- `0x1800209fc`
- `0x18005b148`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005b3f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b3f6`
- `OLEAUT32!__imp_VariantInit` at `0x18005b272`
- `OLEAUT32!__imp_VariantInit` at `0x18005b272`
- `OLEAUT32!__imp_VariantClear` at `0x18005b2c5`
- `OLEAUT32!__imp_VariantClear` at `0x18005b401`
- `OLEAUT32!__imp_VariantClear` at `0x18005b2c5`
- `OLEAUT32!__imp_VariantClear` at `0x18005b401`

## string_xrefs

- `0x18005b4e4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005b43c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b451`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b466`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b47b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b490`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b4a5`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b4ba`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005b4cf`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall Windows::Service::Task::AddWnfTriggerDelay(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  HRESULT result; // eax
  int i; // edi
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  OLECHAR *v19; // rcx
  BSTR v20; // rax
  int v21; // r9d
  int v22; // r8d
  int v23; // eax
  int v24; // [rsp+20h] [rbp-49h] BYREF
  int v25; // [rsp+24h] [rbp-45h] BYREF
  __int64 *v26; // [rsp+28h] [rbp-41h] BYREF
  __int64 v27; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v28; // [rsp+38h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 v31[8]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v32; // [rsp+70h] [rbp+7h]
  __int64 v33; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v28 = 0;
  v7 = *(__int64 **)a1;
  v8 = *v7;
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 72))(v7, &v28);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v9,
      v24);
  v24 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, int *))(*v28 + 56))(v28, &v24);
  if ( result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)result,
      v24);
  for ( i = 1; i <= v24; ++i )
  {
    v27 = 0;
    v12 = *v28;
    v27 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v12 + 64))(v28, (unsigned int)i, &v27);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x157,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v13,
        v24);
    v25 = 0;
    result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 56LL))(v27, &v25);
    if ( result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)result,
        v24);
    if ( v25 == 12 )
    {
      v26 = 0;
      v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v27)(
              v27,
              &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f,
              &v26);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v14,
          v24);
      VariantInit(&pvarg);
      pvarg.vt = 27;
      v15 = (*(__int64 (__fastcall **)(__int64 *, CY *))(*v26 + 176))(v26, &pvarg.cyVal);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
          (const char *)(unsigned int)v15,
          v24);
      if ( *pvarg.bstrVal == 1 && *(_DWORD *)(pvarg.llVal + 24) == 8 && *a2 == **(_QWORD **)(pvarg.llVal + 16) )
      {
        *(_OWORD *)v31 = 0;
        v32 = 0;
        v33 = 0;
        v16 = StringCchPrintfW(v31, 0x14u, L"PT%dM", a4);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16C,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
            (const char *)(unsigned int)v16,
            v24);
        bstrString = 0;
        v17 = *v26;
        bstrString = 0;
        v18 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v17 + 160))(v26, &bstrString);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x170,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
            (const char *)(unsigned int)v18,
            v24);
        v19 = bstrString;
        v20 = bstrString;
        do
        {
          v21 = *(BSTR)((char *)v20 + (char *)v31 - (char *)bstrString);
          v22 = *v20 - v21;
          if ( v22 )
            break;
          ++v20;
        }
        while ( v21 );
        if ( v22 )
        {
          v23 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *))(*v26 + 168))(v26, v31);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x173,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
              (const char *)(unsigned int)v23,
              v24);
          *(_BYTE *)(a1 + 40) = 1;
          v19 = bstrString;
        }
        if ( v19 )
          SysFreeString(v19);
        result = VariantClear(&pvarg);
        if ( v26 )
          result = (*(__int64 (__fastcall **)(__int64 *))(*v26 + 16))(v26);
        if ( v27 )
          result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        break;
      }
      result = VariantClear(&pvarg);
      if ( v26 )
        result = (*(__int64 (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    }
    if ( v27 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( v28 )
    return (*(__int64 (__fastcall **)(__int64 *))(*v28 + 16))(v28);
  return result;
}

```

## disassembly

```asm
0x18005b148  push    rbp
0x18005b14a  push    rbx
0x18005b14b  push    rsi
0x18005b14c  push    rdi
0x18005b14d  push    r12
0x18005b14f  push    r14
0x18005b151  lea     rbp, [rsp-2Fh]
0x18005b156  sub     rsp, 98h
0x18005b15d  mov     rax, cs:__security_cookie
0x18005b164  xor     rax, rsp
0x18005b167  mov     [rbp+57h+var_38], rax
0x18005b16b  mov     ebx, r9d
0x18005b16e  mov     rsi, rdx
0x18005b171  mov     r14, rcx
0x18005b174  mov     [rbp+57h+var_88], 0
0x18005b17c  mov     rcx, [rcx]
0x18005b17f  mov     rax, [rcx]
0x18005b182  mov     [rbp+57h+var_88], 0
0x18005b18a  lea     rdx, [rbp+57h+var_88]
0x18005b18e  mov     rax, [rax+48h]
0x18005b192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b197  mov     rcx, [rbp+5Fh]; this
0x18005b19b  test    eax, eax
0x18005b19d  js      loc_18005B463
0x18005b1a3  mov     [rbp+57h+var_A0], 0
0x18005b1aa  mov     rcx, [rbp+57h+var_88]
0x18005b1ae  mov     rax, [rcx]
0x18005b1b1  lea     rdx, [rbp+57h+var_A0]
0x18005b1b5  mov     rax, [rax+38h]
0x18005b1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b1be  mov     rcx, [rbp+5Fh]; this
0x18005b1c2  test    eax, eax
0x18005b1c4  js      loc_18005B478
0x18005b1ca  mov     r12d, 1
0x18005b1d0  mov     edi, r12d
0x18005b1d3  cmp     [rbp+57h+var_A0], r12d
0x18005b1d7  jl      loc_18005B304
0x18005b1dd  mov     [rbp+57h+var_90], 0
0x18005b1e5  mov     rcx, [rbp+57h+var_88]
0x18005b1e9  mov     rax, [rcx]
0x18005b1ec  mov     [rbp+57h+var_90], 0
0x18005b1f4  lea     r8, [rbp+57h+var_90]
0x18005b1f8  mov     edx, edi
0x18005b1fa  mov     rax, [rax+40h]
0x18005b1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b203  mov     rcx, [rbp+5Fh]; this
0x18005b207  test    eax, eax
0x18005b209  js      loc_18005B44E
0x18005b20f  mov     [rbp+57h+var_9C], 0
0x18005b216  mov     rcx, [rbp+57h+var_90]
0x18005b21a  mov     rax, [rcx]
0x18005b21d  lea     rdx, [rbp+57h+var_9C]
0x18005b221  mov     rax, [rax+38h]
0x18005b225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b22a  mov     rcx, [rbp+5Fh]; this
0x18005b22e  test    eax, eax
0x18005b230  js      loc_18005B439
0x18005b236  cmp     [rbp+57h+var_9C], 0Ch
0x18005b23a  jnz     loc_18005B2E2
0x18005b240  mov     rcx, [rbp+57h+var_90]
0x18005b244  mov     [rbp+57h+var_98], 0
0x18005b24c  mov     rax, [rcx]
0x18005b24f  lea     r8, [rbp+57h+var_98]
0x18005b253  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x18005b25a  mov     rax, [rax]
0x18005b25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b262  mov     rcx, [rbp+5Fh]; this
0x18005b266  test    eax, eax
0x18005b268  js      loc_18005B4E1
0x18005b26e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005b272  call    cs:__imp_VariantInit
0x18005b278  nop
0x18005b279  mov     eax, 1Bh
0x18005b27e  mov     word ptr [rbp+57h+pvarg], ax
0x18005b282  mov     rcx, [rbp+57h+var_98]
0x18005b286  mov     rax, [rcx]
0x18005b289  lea     rdx, [rbp+57h+pvarg+8]
0x18005b28d  mov     rax, [rax+0B0h]
0x18005b294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b299  mov     rcx, [rbp+5Fh]; this
0x18005b29d  test    eax, eax
0x18005b29f  js      loc_18005B4CC
0x18005b2a5  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18005b2a9  cmp     [rcx], r12w
0x18005b2ad  jnz     short loc_18005B2C1
0x18005b2af  cmp     dword ptr [rcx+18h], 8
0x18005b2b3  jnz     short loc_18005B2C1
0x18005b2b5  mov     rcx, [rcx+10h]
0x18005b2b9  mov     rax, [rsi]
0x18005b2bc  cmp     rax, [rcx]
0x18005b2bf  jz      short loc_18005B336
0x18005b2c1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005b2c5  call    cs:__imp_VariantClear
0x18005b2cb  nop
0x18005b2cc  mov     rcx, [rbp+57h+var_98]
0x18005b2d0  test    rcx, rcx
0x18005b2d3  jz      short loc_18005B2E2
0x18005b2d5  mov     rax, [rcx]
0x18005b2d8  mov     rax, [rax+10h]
0x18005b2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2e1  nop
0x18005b2e2  mov     rcx, [rbp+57h+var_90]
0x18005b2e6  test    rcx, rcx
0x18005b2e9  jz      short loc_18005B2F8
0x18005b2eb  mov     rax, [rcx]
0x18005b2ee  mov     rax, [rax+10h]
0x18005b2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2f7  nop
0x18005b2f8  add     edi, r12d
0x18005b2fb  cmp     edi, [rbp+57h+var_A0]
0x18005b2fe  jle     loc_18005B1DD
0x18005b304  mov     rcx, [rbp+57h+var_88]
0x18005b308  test    rcx, rcx
0x18005b30b  jz      short loc_18005B31A
0x18005b30d  mov     rax, [rcx]
0x18005b310  mov     rax, [rax+10h]
0x18005b314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b319  nop
0x18005b31a  mov     rcx, [rbp+57h+var_38]
0x18005b31e  xor     rcx, rsp; StackCookie
0x18005b321  call    __security_check_cookie
0x18005b326  add     rsp, 98h
0x18005b32d  pop     r14
0x18005b32f  pop     r12
0x18005b331  pop     rdi
0x18005b332  pop     rsi
0x18005b333  pop     rbx
0x18005b334  pop     rbp
0x18005b335  retn
0x18005b336  xorps   xmm0, xmm0
0x18005b339  xor     eax, eax
0x18005b33b  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18005b33f  movups  [rbp+57h+var_50], xmm0
0x18005b343  mov     [rbp+57h+var_40], rax
0x18005b347  mov     r9d, ebx
0x18005b34a  lea     r8, aPtDm; "PT%dM"
0x18005b351  lea     edx, [rax+14h]; unsigned __int64
0x18005b354  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18005b358  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b35d  mov     rcx, [rbp+5Fh]; this
0x18005b361  test    eax, eax
0x18005b363  js      loc_18005B48D
0x18005b369  mov     [rbp+57h+bstrString], 0
0x18005b371  mov     rcx, [rbp+57h+var_98]
0x18005b375  mov     rax, [rcx]
0x18005b378  mov     [rbp+57h+bstrString], 0
0x18005b380  lea     rdx, [rbp+57h+bstrString]
0x18005b384  mov     rax, [rax+0A0h]
0x18005b38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b390  mov     rcx, [rbp+5Fh]; this
0x18005b394  test    eax, eax
0x18005b396  js      loc_18005B4A2
0x18005b39c  mov     rcx, [rbp+57h+bstrString]
0x18005b3a0  mov     rax, rcx
0x18005b3a3  lea     rdx, [rbp+57h+var_60]
0x18005b3a7  sub     rdx, rcx
0x18005b3aa  movzx   r8d, word ptr [rax]
0x18005b3ae  movzx   r9d, word ptr [rax+rdx]
0x18005b3b3  sub     r8d, r9d
0x18005b3b6  jnz     short loc_18005B3C1
0x18005b3b8  add     rax, 2
0x18005b3bc  test    r9d, r9d
0x18005b3bf  jnz     short loc_18005B3AA
0x18005b3c1  test    r8d, r8d
0x18005b3c4  jz      short loc_18005B3F1
0x18005b3c6  mov     rcx, [rbp+57h+var_98]
0x18005b3ca  mov     rax, [rcx]
0x18005b3cd  lea     rdx, [rbp+57h+var_60]
0x18005b3d1  mov     rax, [rax+0A8h]
0x18005b3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3dd  mov     rcx, [rbp+5Fh]; this
0x18005b3e1  test    eax, eax
0x18005b3e3  js      loc_18005B4B7
0x18005b3e9  mov     [r14+28h], r12b
0x18005b3ed  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005b3f1  test    rcx, rcx
0x18005b3f4  jz      short loc_18005B3FD
0x18005b3f6  call    cs:__imp_SysFreeString
0x18005b3fc  nop
0x18005b3fd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005b401  call    cs:__imp_VariantClear
0x18005b407  nop
0x18005b408  mov     rcx, [rbp+57h+var_98]
0x18005b40c  test    rcx, rcx
0x18005b40f  jz      short loc_18005B41E
0x18005b411  mov     rax, [rcx]
0x18005b414  mov     rax, [rax+10h]
0x18005b418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b41d  nop
0x18005b41e  mov     rcx, [rbp+57h+var_90]
0x18005b422  test    rcx, rcx
0x18005b425  jz      short loc_18005B434
0x18005b427  mov     rax, [rcx]
0x18005b42a  mov     rax, [rax+10h]
0x18005b42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b433  nop
0x18005b434  jmp     loc_18005B304
0x18005b439  mov     r9d, eax; char *
0x18005b43c  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b443  mov     edx, 15Ah; void *
0x18005b448  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b44e  mov     r9d, eax; char *
0x18005b451  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b458  mov     edx, 157h; void *
0x18005b45d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b463  mov     r9d, eax; char *
0x18005b466  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b46d  mov     edx, 14Fh; void *
0x18005b472  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b478  mov     r9d, eax; char *
0x18005b47b  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b482  mov     edx, 152h; void *
0x18005b487  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b48d  mov     r9d, eax; char *
0x18005b490  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b497  mov     edx, 16Ch; void *
0x18005b49c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b4a2  mov     r9d, eax; char *
0x18005b4a5  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b4ac  mov     edx, 170h; void *
0x18005b4b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b4b7  mov     r9d, eax; char *
0x18005b4ba  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b4c1  mov     edx, 173h; void *
0x18005b4c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b4cc  mov     r9d, eax; char *
0x18005b4cf  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005b4d6  mov     edx, 161h; void *
0x18005b4db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005b4e1  mov     r9d, eax; char *
0x18005b4e4  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005b4eb  mov     edx, 1CBEh; void *
0x18005b4f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
