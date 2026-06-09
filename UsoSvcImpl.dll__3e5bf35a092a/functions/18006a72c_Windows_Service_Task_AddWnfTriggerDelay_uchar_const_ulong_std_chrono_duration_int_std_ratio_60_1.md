# Windows::Service::Task::AddWnfTriggerDelay(uchar const *,ulong,std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x18006a72c`
- end: `0x18006aaf5`
- name: `?AddWnfTriggerDelay@Task@Service@Windows@@QEAAXPEBEKV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@Z`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c1e0`

## callees

- `0x18000775c`
- `0x1800112d0`
- `0x18006a72c`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006a9f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a9f5`
- `OLEAUT32!__imp_VariantInit` at `0x18006a860`
- `OLEAUT32!__imp_VariantInit` at `0x18006a860`
- `OLEAUT32!__imp_VariantClear` at `0x18006a8b7`
- `OLEAUT32!__imp_VariantClear` at `0x18006aa00`
- `OLEAUT32!__imp_VariantClear` at `0x18006a8b7`
- `OLEAUT32!__imp_VariantClear` at `0x18006aa00`

## string_xrefs

- `0x18006aae3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18006aa3b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aa50`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aa65`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aa7a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aa8f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aaa4`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aab9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006aace`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

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
0x18006a72c  mov     rax, rsp
0x18006a72f  mov     [rax+10h], rbx
0x18006a733  mov     [rax+18h], rsi
0x18006a737  mov     [rax+20h], rdi
0x18006a73b  push    rbp
0x18006a73c  push    r12
0x18006a73e  push    r14
0x18006a740  lea     rbp, [rax-5Fh]
0x18006a744  sub     rsp, 90h
0x18006a74b  mov     rax, cs:__security_cookie
0x18006a752  xor     rax, rsp
0x18006a755  mov     [rbp+57h+var_18], rax
0x18006a759  mov     ebx, r9d
0x18006a75c  mov     rsi, rdx
0x18006a75f  mov     r14, rcx
0x18006a762  mov     [rbp+57h+var_50], 0
0x18006a76a  mov     rcx, [rcx]
0x18006a76d  mov     rax, [rcx]
0x18006a770  mov     [rbp+57h+var_50], 0
0x18006a778  lea     rdx, [rbp+57h+var_50]
0x18006a77c  mov     rax, [rax+48h]
0x18006a780  call    _guard_dispatch_icall
0x18006a785  mov     rcx, [rbp+5Fh]; this
0x18006a789  test    eax, eax
0x18006a78b  js      loc_18006AA62
0x18006a791  mov     [rbp+57h+var_68], 0
0x18006a798  mov     rcx, [rbp+57h+var_50]
0x18006a79c  mov     rax, [rcx]
0x18006a79f  lea     rdx, [rbp+57h+var_68]
0x18006a7a3  mov     rax, [rax+38h]
0x18006a7a7  call    _guard_dispatch_icall
0x18006a7ac  mov     rcx, [rbp+5Fh]; this
0x18006a7b0  test    eax, eax
0x18006a7b2  js      loc_18006AA77
0x18006a7b8  mov     r12d, 1
0x18006a7be  mov     edi, r12d
0x18006a7c1  cmp     [rbp+57h+var_68], r12d
0x18006a7c5  jl      loc_18006A8F6
0x18006a7cb  mov     [rbp+57h+var_58], 0
0x18006a7d3  mov     rcx, [rbp+57h+var_50]
0x18006a7d7  mov     rax, [rcx]
0x18006a7da  mov     [rbp+57h+var_58], 0
0x18006a7e2  lea     r8, [rbp+57h+var_58]
0x18006a7e6  mov     edx, edi
0x18006a7e8  mov     rax, [rax+40h]
0x18006a7ec  call    _guard_dispatch_icall
0x18006a7f1  mov     rcx, [rbp+5Fh]; this
0x18006a7f5  test    eax, eax
0x18006a7f7  js      loc_18006AA4D
0x18006a7fd  mov     [rbp+57h+var_64], 0
0x18006a804  mov     rcx, [rbp+57h+var_58]
0x18006a808  mov     rax, [rcx]
0x18006a80b  lea     rdx, [rbp+57h+var_64]
0x18006a80f  mov     rax, [rax+38h]
0x18006a813  call    _guard_dispatch_icall
0x18006a818  mov     rcx, [rbp+5Fh]; this
0x18006a81c  test    eax, eax
0x18006a81e  js      loc_18006AA38
0x18006a824  cmp     [rbp+57h+var_64], 0Ch
0x18006a828  jnz     loc_18006A8D4
0x18006a82e  mov     rcx, [rbp+57h+var_58]
0x18006a832  mov     [rbp+57h+var_60], 0
0x18006a83a  mov     rax, [rcx]
0x18006a83d  lea     r8, [rbp+57h+var_60]
0x18006a841  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x18006a848  mov     rax, [rax]
0x18006a84b  call    _guard_dispatch_icall
0x18006a850  mov     rcx, [rbp+5Fh]; this
0x18006a854  test    eax, eax
0x18006a856  js      loc_18006AAE0
0x18006a85c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006a860  call    cs:__imp_VariantInit
0x18006a866  nop
0x18006a867  mov     eax, 1Bh
0x18006a86c  mov     word ptr [rbp+57h+pvarg], ax
0x18006a870  mov     rcx, [rbp+57h+var_60]
0x18006a874  mov     rax, [rcx]
0x18006a877  lea     rdx, [rbp+57h+pvarg+8]
0x18006a87b  mov     rax, [rax+0B0h]
0x18006a882  call    _guard_dispatch_icall
0x18006a887  mov     rcx, [rbp+5Fh]; this
0x18006a88b  test    eax, eax
0x18006a88d  js      loc_18006AACB
0x18006a893  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x18006a897  cmp     [rcx], r12w
0x18006a89b  jnz     short loc_18006A8B3
0x18006a89d  cmp     dword ptr [rcx+18h], 8
0x18006a8a1  jnz     short loc_18006A8B3
0x18006a8a3  mov     rcx, [rcx+10h]
0x18006a8a7  mov     rax, [rsi]
0x18006a8aa  cmp     rax, [rcx]
0x18006a8ad  jz      loc_18006A935
0x18006a8b3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006a8b7  call    cs:__imp_VariantClear
0x18006a8bd  nop
0x18006a8be  mov     rcx, [rbp+57h+var_60]
0x18006a8c2  test    rcx, rcx
0x18006a8c5  jz      short loc_18006A8D4
0x18006a8c7  mov     rax, [rcx]
0x18006a8ca  mov     rax, [rax+10h]
0x18006a8ce  call    _guard_dispatch_icall
0x18006a8d3  nop
0x18006a8d4  mov     rcx, [rbp+57h+var_58]
0x18006a8d8  test    rcx, rcx
0x18006a8db  jz      short loc_18006A8EA
0x18006a8dd  mov     rax, [rcx]
0x18006a8e0  mov     rax, [rax+10h]
0x18006a8e4  call    _guard_dispatch_icall
0x18006a8e9  nop
0x18006a8ea  add     edi, r12d
0x18006a8ed  cmp     edi, [rbp+57h+var_68]
0x18006a8f0  jle     loc_18006A7CB
0x18006a8f6  mov     rcx, [rbp+57h+var_50]
0x18006a8fa  test    rcx, rcx
0x18006a8fd  jz      short loc_18006A90C
0x18006a8ff  mov     rax, [rcx]
0x18006a902  mov     rax, [rax+10h]
0x18006a906  call    _guard_dispatch_icall
0x18006a90b  nop
0x18006a90c  mov     rcx, [rbp+57h+var_18]
0x18006a910  xor     rcx, rsp; StackCookie
0x18006a913  call    __security_check_cookie
0x18006a918  lea     r11, [rsp+0A0h+var_10]
0x18006a920  mov     rbx, [r11+28h]
0x18006a924  mov     rsi, [r11+30h]
0x18006a928  mov     rdi, [r11+38h]
0x18006a92c  mov     rsp, r11
0x18006a92f  pop     r14
0x18006a931  pop     r12
0x18006a933  pop     rbp
0x18006a934  retn
0x18006a935  xorps   xmm0, xmm0
0x18006a938  xor     eax, eax
0x18006a93a  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18006a93e  movups  [rbp+57h+var_30], xmm0
0x18006a942  mov     [rbp+57h+var_20], rax
0x18006a946  mov     r9d, ebx
0x18006a949  lea     r8, aPtDm; "PT%dM"
0x18006a950  lea     edx, [rax+14h]; unsigned __int64
0x18006a953  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18006a957  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18006a95c  mov     rcx, [rbp+5Fh]; this
0x18006a960  test    eax, eax
0x18006a962  js      loc_18006AA8C
0x18006a968  mov     [rbp+57h+bstrString], 0
0x18006a970  mov     rcx, [rbp+57h+var_60]
0x18006a974  mov     rax, [rcx]
0x18006a977  mov     [rbp+57h+bstrString], 0
0x18006a97f  lea     rdx, [rbp+57h+bstrString]
0x18006a983  mov     rax, [rax+0A0h]
0x18006a98a  call    _guard_dispatch_icall
0x18006a98f  mov     rcx, [rbp+5Fh]; this
0x18006a993  test    eax, eax
0x18006a995  js      loc_18006AAA1
0x18006a99b  mov     rcx, [rbp+57h+bstrString]
0x18006a99f  mov     rax, rcx
0x18006a9a2  lea     rdx, [rbp+57h+Buffer]
0x18006a9a6  sub     rdx, rcx
0x18006a9a9  movzx   r8d, word ptr [rax]
0x18006a9ad  movzx   r9d, word ptr [rax+rdx]
0x18006a9b2  sub     r8d, r9d
0x18006a9b5  jnz     short loc_18006A9C0
0x18006a9b7  add     rax, 2
0x18006a9bb  test    r9d, r9d
0x18006a9be  jnz     short loc_18006A9A9
0x18006a9c0  test    r8d, r8d
0x18006a9c3  jz      short loc_18006A9F0
0x18006a9c5  mov     rcx, [rbp+57h+var_60]
0x18006a9c9  mov     rax, [rcx]
0x18006a9cc  lea     rdx, [rbp+57h+Buffer]
0x18006a9d0  mov     rax, [rax+0A8h]
0x18006a9d7  call    _guard_dispatch_icall
0x18006a9dc  mov     rcx, [rbp+5Fh]; this
0x18006a9e0  test    eax, eax
0x18006a9e2  js      loc_18006AAB6
0x18006a9e8  mov     [r14+28h], r12b
0x18006a9ec  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18006a9f0  test    rcx, rcx
0x18006a9f3  jz      short loc_18006A9FC
0x18006a9f5  call    cs:__imp_SysFreeString
0x18006a9fb  nop
0x18006a9fc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006aa00  call    cs:__imp_VariantClear
0x18006aa06  nop
0x18006aa07  mov     rcx, [rbp+57h+var_60]
0x18006aa0b  test    rcx, rcx
0x18006aa0e  jz      short loc_18006AA1D
0x18006aa10  mov     rax, [rcx]
0x18006aa13  mov     rax, [rax+10h]
0x18006aa17  call    _guard_dispatch_icall
0x18006aa1c  nop
0x18006aa1d  mov     rcx, [rbp+57h+var_58]
0x18006aa21  test    rcx, rcx
0x18006aa24  jz      short loc_18006AA33
0x18006aa26  mov     rax, [rcx]
0x18006aa29  mov     rax, [rax+10h]
0x18006aa2d  call    _guard_dispatch_icall
0x18006aa32  nop
0x18006aa33  jmp     loc_18006A8F6
0x18006aa38  mov     r9d, eax; char *
0x18006aa3b  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aa42  mov     edx, 170h; void *
0x18006aa47  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aa4d  mov     r9d, eax; char *
0x18006aa50  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aa57  mov     edx, 16Dh; void *
0x18006aa5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aa62  mov     r9d, eax; char *
0x18006aa65  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aa6c  mov     edx, 165h; void *
0x18006aa71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aa77  mov     r9d, eax; char *
0x18006aa7a  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aa81  mov     edx, 168h; void *
0x18006aa86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aa8c  mov     r9d, eax; char *
0x18006aa8f  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aa96  mov     edx, 182h; void *
0x18006aa9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aaa1  mov     r9d, eax; char *
0x18006aaa4  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aaab  mov     edx, 186h; void *
0x18006aab0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aab6  mov     r9d, eax; char *
0x18006aab9  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aac0  mov     edx, 189h; void *
0x18006aac5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aacb  mov     r9d, eax; char *
0x18006aace  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006aad5  mov     edx, 177h; void *
0x18006aada  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006aae0  mov     r9d, eax; char *
0x18006aae3  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006aaea  mov     edx, 1C96h; void *
0x18006aaef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
