# WaasMedic::TasksHelper::RunTask(ushort const *)

- ea: `0x180060284`
- end: `0x180060439`
- name: `?RunTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `437`
- prototype: `__int64 __fastcall(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180054390`

## callees

- `0x1800023b0`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180060284`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800602a8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800602a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180060423`
- `OLEAUT32!__imp_SysFreeString` at `0x180060423`
- `OLEAUT32!__imp_VariantInit` at `0x180060330`
- `OLEAUT32!__imp_VariantInit` at `0x180060330`
- `OLEAUT32!__imp_VariantClear` at `0x180060361`
- `OLEAUT32!__imp_VariantClear` at `0x180060361`

## string_xrefs

- `0x18006029e`: `StartComponentCleanup`
- `0x1800602cf`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x180060375`: `Failed to run task %s! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaasMedic::TasksHelper::RunTask(WaasMedic::TasksHelper *this, const unsigned __int16 *a2)
{
  BSTR v3; // rax
  OLECHAR *v4; // rbx
  int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, VARIANTARG *, _QWORD); // rdi
  __int64 v9; // rdx
  const struct _tlgProvider_t *v10; // rax
  int v11; // r9d
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-39h]
  _QWORD v15[2]; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-9h] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v19; // [rsp+C0h] [rbp+67h] BYREF
  const unsigned __int16 *v20; // [rsp+C8h] [rbp+6Fh] BYREF
  const OLECHAR *v21; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int16 *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  v20 = a2;
  v3 = SysAllocString(L"StartComponentCleanup");
  v4 = v3;
  v15[1] = v3;
  v19 = 0;
  if ( *((_BYTE *)this + 17) )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**((_QWORD **)this + 1) + 104LL))(
           *((_QWORD *)this + 1),
           v3,
           &v19);
    if ( v5 < 0
      || (v7 = v19,
          v8 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v19 + 96LL),
          VariantInit(&pvarg),
          v17 = pvarg,
          v5 = v8(v7, &v17, 0),
          VariantClear(&pvarg),
          v5 < 0) )
    {
      LogLevelW(2u, L"Failed to run task %s! hr = 0x%08x", L"StartComponentCleanup", (unsigned int)v5);
      v10 = WaasMedic::TelemetryProvider::Provider();
      if ( *(_DWORD *)v10 > 5u )
      {
        v9 = *((_QWORD *)v10 + 3);
        if ( (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
        {
          LODWORD(v20) = v5;
          v21 = L"StartComponentCleanup";
          v22 = &gc_pszVersionString;
          v15[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v10,
            (unsigned int)&word_18008A5B6,
            0,
            v11,
            (__int64)v15,
            (__int64)&v22,
            (__int64)&v21,
            (__int64)&v20);
        }
      }
    }
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v9);
    }
  }
  else
  {
    v5 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x8007139FLL,
      v14);
    v6 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  SysFreeString(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180060284  mov     [rsp-8+arg_8], rdx
0x180060289  push    rbp
0x18006028a  push    rbx
0x18006028b  push    rsi
0x18006028c  push    rdi
0x18006028d  push    r15
0x18006028f  lea     rbp, [rsp-37h]
0x180060294  sub     rsp, 90h
0x18006029b  mov     rdi, rcx
0x18006029e  lea     r15, aStartcomponent; "StartComponentCleanup"
0x1800602a5  mov     rcx, r15; psz
0x1800602a8  call    cs:__imp_SysAllocString
0x1800602ae  mov     rbx, rax
0x1800602b1  mov     [rbp+57h+var_68], rax
0x1800602b5  mov     [rbp+57h+arg_0], 0
0x1800602bd  cmp     byte ptr [rdi+11h], 0
0x1800602c1  jnz     short loc_180060304
0x1800602c3  mov     rcx, [rbp+5Fh]; this
0x1800602c7  mov     edi, 8007139Fh
0x1800602cc  mov     r9d, edi; char *
0x1800602cf  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800602d6  mov     edx, 132h; void *
0x1800602db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800602e0  nop
0x1800602e1  mov     rcx, [rbp+57h+arg_0]
0x1800602e5  test    rcx, rcx
0x1800602e8  jz      short loc_1800602FF
0x1800602ea  mov     [rbp+57h+arg_0], 0
0x1800602f2  mov     rax, [rcx]
0x1800602f5  mov     rax, [rax+10h]
0x1800602f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602fe  nop
0x1800602ff  jmp     loc_180060420
0x180060304  mov     rcx, [rdi+8]
0x180060308  mov     rax, [rcx]
0x18006030b  lea     r8, [rbp+57h+arg_0]
0x18006030f  mov     rdx, rbx
0x180060312  mov     rax, [rax+68h]
0x180060316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006031b  mov     edi, eax
0x18006031d  test    eax, eax
0x18006031f  js      short loc_18006036F
0x180060321  mov     rsi, [rbp+57h+arg_0]
0x180060325  mov     rax, [rsi]
0x180060328  mov     rdi, [rax+60h]
0x18006032c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060330  call    cs:__imp_VariantInit
0x180060336  nop
0x180060337  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18006033b  movaps  [rbp+57h+var_40], xmm0
0x18006033f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180060344  movsd   [rbp+57h+var_30], xmm1
0x180060349  xor     r8d, r8d
0x18006034c  lea     rdx, [rbp+57h+var_40]
0x180060350  mov     rcx, rsi
0x180060353  mov     rax, rdi
0x180060356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006035b  mov     edi, eax
0x18006035d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060361  call    cs:__imp_VariantClear
0x180060367  test    edi, edi
0x180060369  jns     loc_180060402
0x18006036f  mov     r9d, edi
0x180060372  mov     r8, r15
0x180060375  lea     rdx, aFailedToRunTas; "Failed to run task %s! hr = 0x%08x"
0x18006037c  mov     ecx, 2; unsigned __int8
0x180060381  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180060386  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18006038b  mov     ecx, [rax]
0x18006038d  cmp     ecx, 5
0x180060390  jbe     short loc_180060402
0x180060392  mov     rdx, [rax+18h]
0x180060396  mov     rcx, [rax+10h]
0x18006039a  mov     r8, 400000000000h
0x1800603a4  test    r8, rcx
0x1800603a7  jz      short loc_180060402
0x1800603a9  mov     rcx, rdx
0x1800603ac  and     rcx, r8
0x1800603af  cmp     rcx, rdx
0x1800603b2  jnz     short loc_180060402
0x1800603b4  mov     dword ptr [rbp+57h+arg_8], edi
0x1800603b7  mov     [rbp+57h+arg_10], r15
0x1800603bb  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800603c2  mov     [rbp+57h+arg_18], rcx
0x1800603c6  mov     [rbp+57h+var_70], 1000000h
0x1800603ce  lea     rcx, [rbp+57h+arg_8]
0x1800603d2  mov     [rsp+0B0h+var_78], rcx
0x1800603d7  lea     rcx, [rbp+57h+arg_10]
0x1800603db  mov     [rsp+0B0h+var_80], rcx
0x1800603e0  lea     rcx, [rbp+57h+arg_18]
0x1800603e4  mov     [rsp+0B0h+var_88], rcx
0x1800603e9  lea     rcx, [rbp+57h+var_70]
0x1800603ed  mov     [rsp+0B0h+var_90], rcx
0x1800603f2  lea     rdx, word_18008A5B6
0x1800603f9  mov     rcx, rax
0x1800603fc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180060401  nop
0x180060402  mov     rcx, [rbp+57h+arg_0]
0x180060406  test    rcx, rcx
0x180060409  jz      short loc_180060420
0x18006040b  mov     [rbp+57h+arg_0], 0
0x180060413  mov     rax, [rcx]
0x180060416  mov     rax, [rax+10h]
0x18006041a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006041f  nop
0x180060420  mov     rcx, rbx; bstrString
0x180060423  call    cs:__imp_SysFreeString
0x180060429  mov     eax, edi
0x18006042b  add     rsp, 90h
0x180060432  pop     r15
0x180060434  pop     rdi
0x180060435  pop     rsi
0x180060436  pop     rbx
0x180060437  pop     rbp
0x180060438  retn
```
