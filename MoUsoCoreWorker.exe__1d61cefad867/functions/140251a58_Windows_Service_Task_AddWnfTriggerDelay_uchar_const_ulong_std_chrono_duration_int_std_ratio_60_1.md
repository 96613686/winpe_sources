# Windows::Service::Task::AddWnfTriggerDelay(uchar const *,ulong,std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x140251a58`
- end: `0x140251e21`
- name: `?AddWnfTriggerDelay@Task@Service@Windows@@QEAAXPEBEKV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@Z`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140253510`

## callees

- `0x1400413a8`
- `0x140041430`
- `0x140251a58`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140251d21`
- `OLEAUT32!__imp_SysFreeString` at `0x140251d21`
- `OLEAUT32!__imp_VariantInit` at `0x140251b8c`
- `OLEAUT32!__imp_VariantInit` at `0x140251b8c`
- `OLEAUT32!__imp_VariantClear` at `0x140251be3`
- `OLEAUT32!__imp_VariantClear` at `0x140251d2c`
- `OLEAUT32!__imp_VariantClear` at `0x140251be3`
- `OLEAUT32!__imp_VariantClear` at `0x140251d2c`

## string_xrefs

- `0x140251e0f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140251d67`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251d7c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251d91`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251da6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251dbb`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251dd0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251de5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251dfa`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  VARIANTARG pvarg; // [rsp+28h] [rbp-29h] BYREF
  int v25; // [rsp+40h] [rbp-11h] BYREF
  int v26; // [rsp+44h] [rbp-Dh] BYREF
  __int64 *v27; // [rsp+48h] [rbp-9h] BYREF
  __int64 v28; // [rsp+50h] [rbp-1h] BYREF
  __int64 *v29; // [rsp+58h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+Fh] BYREF
  wchar_t Buffer[8]; // [rsp+68h] [rbp+17h] BYREF
  __int128 v32; // [rsp+78h] [rbp+27h]
  __int64 v33; // [rsp+88h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v29 = 0;
  v7 = *(__int64 **)a1;
  v8 = *v7;
  v29 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 72))(v7, &v29);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v9,
      *(int *)&pvarg.vt);
  v25 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, int *))(*v29 + 56))(v29, &v25);
  if ( result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)result,
      *(int *)&pvarg.vt);
  for ( i = 1; i <= v25; ++i )
  {
    v28 = 0;
    v12 = *v29;
    v28 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v12 + 64))(v29, (unsigned int)i, &v28);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v13,
        *(int *)&pvarg.vt);
    v26 = 0;
    result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 56LL))(v28, &v26);
    if ( result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)result,
        *(int *)&pvarg.vt);
    if ( v26 == 12 )
    {
      v27 = 0;
      v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v28)(
              v28,
              &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f,
              &v27);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v14,
          *(int *)&pvarg.vt);
      VariantInit(&pvarg);
      pvarg.vt = 27;
      v15 = (*(__int64 (__fastcall **)(__int64 *, CY *))(*v27 + 176))(v27, &pvarg.cyVal);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
          (const char *)(unsigned int)v15,
          *(int *)&pvarg.vt);
      if ( *pvarg.bstrVal == 1 && *(_DWORD *)(pvarg.llVal + 24) == 8 && *a2 == **(_QWORD **)(pvarg.llVal + 16) )
      {
        *(_OWORD *)Buffer = 0;
        v32 = 0;
        v33 = 0;
        v16 = StringCchPrintfW(Buffer, 0x14u, L"PT%dM", a4);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v16,
            *(int *)&pvarg.vt);
        bstrString = 0;
        v17 = *v27;
        bstrString = 0;
        v18 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v17 + 160))(v27, &bstrString);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x186,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v18,
            *(int *)&pvarg.vt);
        v19 = bstrString;
        v20 = bstrString;
        do
        {
          v21 = *(BSTR)((char *)v20 + (char *)Buffer - (char *)bstrString);
          v22 = *v20 - v21;
          if ( v22 )
            break;
          ++v20;
        }
        while ( v21 );
        if ( v22 )
        {
          v23 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *))(*v27 + 168))(v27, Buffer);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x189,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
              (const char *)(unsigned int)v23,
              *(int *)&pvarg.vt);
          *(_BYTE *)(a1 + 40) = 1;
          v19 = bstrString;
        }
        if ( v19 )
          SysFreeString(v19);
        result = VariantClear(&pvarg);
        if ( v27 )
          result = (*(__int64 (__fastcall **)(__int64 *))(*v27 + 16))(v27);
        if ( v28 )
          result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        break;
      }
      result = VariantClear(&pvarg);
      if ( v27 )
        result = (*(__int64 (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    }
    if ( v28 )
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( v29 )
    return (*(__int64 (__fastcall **)(__int64 *))(*v29 + 16))(v29);
  return result;
}

```

## disassembly

```asm
0x140251a58  mov     rax, rsp
0x140251a5b  mov     [rax+10h], rbx
0x140251a5f  mov     [rax+18h], rsi
0x140251a63  mov     [rax+20h], rdi
0x140251a67  push    rbp
0x140251a68  push    r12
0x140251a6a  push    r14
0x140251a6c  lea     rbp, [rax-5Fh]
0x140251a70  sub     rsp, 90h
0x140251a77  mov     rax, cs:__security_cookie
0x140251a7e  xor     rax, rsp
0x140251a81  mov     [rbp+57h+var_18], rax
0x140251a85  mov     ebx, r9d
0x140251a88  mov     rsi, rdx
0x140251a8b  mov     r14, rcx
0x140251a8e  mov     [rbp+57h+var_50], 0
0x140251a96  mov     rcx, [rcx]
0x140251a99  mov     rax, [rcx]
0x140251a9c  mov     [rbp+57h+var_50], 0
0x140251aa4  lea     rdx, [rbp+57h+var_50]
0x140251aa8  mov     rax, [rax+48h]
0x140251aac  call    _guard_dispatch_icall
0x140251ab1  mov     rcx, [rbp+5Fh]; this
0x140251ab5  test    eax, eax
0x140251ab7  js      loc_140251D8E
0x140251abd  mov     [rbp+57h+var_68], 0
0x140251ac4  mov     rcx, [rbp+57h+var_50]
0x140251ac8  mov     rax, [rcx]
0x140251acb  lea     rdx, [rbp+57h+var_68]
0x140251acf  mov     rax, [rax+38h]
0x140251ad3  call    _guard_dispatch_icall
0x140251ad8  mov     rcx, [rbp+5Fh]; this
0x140251adc  test    eax, eax
0x140251ade  js      loc_140251DA3
0x140251ae4  mov     r12d, 1
0x140251aea  mov     edi, r12d
0x140251aed  cmp     [rbp+57h+var_68], r12d
0x140251af1  jl      loc_140251C22
0x140251af7  mov     [rbp+57h+var_58], 0
0x140251aff  mov     rcx, [rbp+57h+var_50]
0x140251b03  mov     rax, [rcx]
0x140251b06  mov     [rbp+57h+var_58], 0
0x140251b0e  lea     r8, [rbp+57h+var_58]
0x140251b12  mov     edx, edi
0x140251b14  mov     rax, [rax+40h]
0x140251b18  call    _guard_dispatch_icall
0x140251b1d  mov     rcx, [rbp+5Fh]; this
0x140251b21  test    eax, eax
0x140251b23  js      loc_140251D79
0x140251b29  mov     [rbp+57h+var_64], 0
0x140251b30  mov     rcx, [rbp+57h+var_58]
0x140251b34  mov     rax, [rcx]
0x140251b37  lea     rdx, [rbp+57h+var_64]
0x140251b3b  mov     rax, [rax+38h]
0x140251b3f  call    _guard_dispatch_icall
0x140251b44  mov     rcx, [rbp+5Fh]; this
0x140251b48  test    eax, eax
0x140251b4a  js      loc_140251D64
0x140251b50  cmp     [rbp+57h+var_64], 0Ch
0x140251b54  jnz     loc_140251C00
0x140251b5a  mov     rcx, [rbp+57h+var_58]
0x140251b5e  mov     [rbp+57h+var_60], 0
0x140251b66  mov     rax, [rcx]
0x140251b69  lea     r8, [rbp+57h+var_60]
0x140251b6d  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x140251b74  mov     rax, [rax]
0x140251b77  call    _guard_dispatch_icall
0x140251b7c  mov     rcx, [rbp+5Fh]; this
0x140251b80  test    eax, eax
0x140251b82  js      loc_140251E0C
0x140251b88  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140251b8c  call    cs:__imp_VariantInit
0x140251b92  nop
0x140251b93  mov     eax, 1Bh
0x140251b98  mov     word ptr [rbp+57h+pvarg], ax
0x140251b9c  mov     rcx, [rbp+57h+var_60]
0x140251ba0  mov     rax, [rcx]
0x140251ba3  lea     rdx, [rbp+57h+pvarg+8]
0x140251ba7  mov     rax, [rax+0B0h]
0x140251bae  call    _guard_dispatch_icall
0x140251bb3  mov     rcx, [rbp+5Fh]; this
0x140251bb7  test    eax, eax
0x140251bb9  js      loc_140251DF7
0x140251bbf  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x140251bc3  cmp     [rcx], r12w
0x140251bc7  jnz     short loc_140251BDF
0x140251bc9  cmp     dword ptr [rcx+18h], 8
0x140251bcd  jnz     short loc_140251BDF
0x140251bcf  mov     rcx, [rcx+10h]
0x140251bd3  mov     rax, [rsi]
0x140251bd6  cmp     rax, [rcx]
0x140251bd9  jz      loc_140251C61
0x140251bdf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140251be3  call    cs:__imp_VariantClear
0x140251be9  nop
0x140251bea  mov     rcx, [rbp+57h+var_60]
0x140251bee  test    rcx, rcx
0x140251bf1  jz      short loc_140251C00
0x140251bf3  mov     rax, [rcx]
0x140251bf6  mov     rax, [rax+10h]
0x140251bfa  call    _guard_dispatch_icall
0x140251bff  nop
0x140251c00  mov     rcx, [rbp+57h+var_58]
0x140251c04  test    rcx, rcx
0x140251c07  jz      short loc_140251C16
0x140251c09  mov     rax, [rcx]
0x140251c0c  mov     rax, [rax+10h]
0x140251c10  call    _guard_dispatch_icall
0x140251c15  nop
0x140251c16  add     edi, r12d
0x140251c19  cmp     edi, [rbp+57h+var_68]
0x140251c1c  jle     loc_140251AF7
0x140251c22  mov     rcx, [rbp+57h+var_50]
0x140251c26  test    rcx, rcx
0x140251c29  jz      short loc_140251C38
0x140251c2b  mov     rax, [rcx]
0x140251c2e  mov     rax, [rax+10h]
0x140251c32  call    _guard_dispatch_icall
0x140251c37  nop
0x140251c38  mov     rcx, [rbp+57h+var_18]
0x140251c3c  xor     rcx, rsp; StackCookie
0x140251c3f  call    __security_check_cookie
0x140251c44  lea     r11, [rsp+0A0h+var_10]
0x140251c4c  mov     rbx, [r11+28h]
0x140251c50  mov     rsi, [r11+30h]
0x140251c54  mov     rdi, [r11+38h]
0x140251c58  mov     rsp, r11
0x140251c5b  pop     r14
0x140251c5d  pop     r12
0x140251c5f  pop     rbp
0x140251c60  retn
0x140251c61  xorps   xmm0, xmm0
0x140251c64  xor     eax, eax
0x140251c66  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x140251c6a  movups  [rbp+57h+var_30], xmm0
0x140251c6e  mov     [rbp+57h+var_20], rax
0x140251c72  mov     r9d, ebx
0x140251c75  lea     r8, aPtDm; "PT%dM"
0x140251c7c  lea     edx, [rax+14h]; unsigned __int64
0x140251c7f  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140251c83  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140251c88  mov     rcx, [rbp+5Fh]; this
0x140251c8c  test    eax, eax
0x140251c8e  js      loc_140251DB8
0x140251c94  mov     [rbp+57h+bstrString], 0
0x140251c9c  mov     rcx, [rbp+57h+var_60]
0x140251ca0  mov     rax, [rcx]
0x140251ca3  mov     [rbp+57h+bstrString], 0
0x140251cab  lea     rdx, [rbp+57h+bstrString]
0x140251caf  mov     rax, [rax+0A0h]
0x140251cb6  call    _guard_dispatch_icall
0x140251cbb  mov     rcx, [rbp+5Fh]; this
0x140251cbf  test    eax, eax
0x140251cc1  js      loc_140251DCD
0x140251cc7  mov     rcx, [rbp+57h+bstrString]
0x140251ccb  mov     rax, rcx
0x140251cce  lea     rdx, [rbp+57h+Buffer]
0x140251cd2  sub     rdx, rcx
0x140251cd5  movzx   r8d, word ptr [rax]
0x140251cd9  movzx   r9d, word ptr [rax+rdx]
0x140251cde  sub     r8d, r9d
0x140251ce1  jnz     short loc_140251CEC
0x140251ce3  add     rax, 2
0x140251ce7  test    r9d, r9d
0x140251cea  jnz     short loc_140251CD5
0x140251cec  test    r8d, r8d
0x140251cef  jz      short loc_140251D1C
0x140251cf1  mov     rcx, [rbp+57h+var_60]
0x140251cf5  mov     rax, [rcx]
0x140251cf8  lea     rdx, [rbp+57h+Buffer]
0x140251cfc  mov     rax, [rax+0A8h]
0x140251d03  call    _guard_dispatch_icall
0x140251d08  mov     rcx, [rbp+5Fh]; this
0x140251d0c  test    eax, eax
0x140251d0e  js      loc_140251DE2
0x140251d14  mov     [r14+28h], r12b
0x140251d18  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140251d1c  test    rcx, rcx
0x140251d1f  jz      short loc_140251D28
0x140251d21  call    cs:__imp_SysFreeString
0x140251d27  nop
0x140251d28  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140251d2c  call    cs:__imp_VariantClear
0x140251d32  nop
0x140251d33  mov     rcx, [rbp+57h+var_60]
0x140251d37  test    rcx, rcx
0x140251d3a  jz      short loc_140251D49
0x140251d3c  mov     rax, [rcx]
0x140251d3f  mov     rax, [rax+10h]
0x140251d43  call    _guard_dispatch_icall
0x140251d48  nop
0x140251d49  mov     rcx, [rbp+57h+var_58]
0x140251d4d  test    rcx, rcx
0x140251d50  jz      short loc_140251D5F
0x140251d52  mov     rax, [rcx]
0x140251d55  mov     rax, [rax+10h]
0x140251d59  call    _guard_dispatch_icall
0x140251d5e  nop
0x140251d5f  jmp     loc_140251C22
0x140251d64  mov     r9d, eax; char *
0x140251d67  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251d6e  mov     edx, 170h; void *
0x140251d73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251d79  mov     r9d, eax; char *
0x140251d7c  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251d83  mov     edx, 16Dh; void *
0x140251d88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251d8e  mov     r9d, eax; char *
0x140251d91  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251d98  mov     edx, 165h; void *
0x140251d9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251da3  mov     r9d, eax; char *
0x140251da6  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251dad  mov     edx, 168h; void *
0x140251db2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251db8  mov     r9d, eax; char *
0x140251dbb  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251dc2  mov     edx, 182h; void *
0x140251dc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251dcd  mov     r9d, eax; char *
0x140251dd0  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251dd7  mov     edx, 186h; void *
0x140251ddc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251de2  mov     r9d, eax; char *
0x140251de5  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251dec  mov     edx, 189h; void *
0x140251df1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251df7  mov     r9d, eax; char *
0x140251dfa  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251e01  mov     edx, 177h; void *
0x140251e06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140251e0c  mov     r9d, eax; char *
0x140251e0f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140251e16  mov     edx, 1C96h; void *
0x140251e1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
