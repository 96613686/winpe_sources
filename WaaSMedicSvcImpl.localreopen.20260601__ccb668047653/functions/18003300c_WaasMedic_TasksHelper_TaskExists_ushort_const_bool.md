# WaasMedic::TasksHelper::TaskExists(ushort const *,bool *)

- ea: `0x18003300c`
- end: `0x1800331fd`
- name: `?TaskExists@TasksHelper@WaasMedic@@QEAAJPEBGPEA_N@Z`
- size: `497`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001fe68`

## callees

- `0x18000263c`
- `0x18000bbd4`
- `0x18000d04c`
- `0x18002e81c`
- `0x18003300c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033039`
- `OLEAUT32!__imp_SysAllocString` at `0x180033039`
- `OLEAUT32!__imp_SysFreeString` at `0x18003306c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18003306c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800331cb`

## string_xrefs

- `0x180033057`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x1800330a4`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18003313a`: `Failed to access task %s! hr = 0x%08x`
- `0x18003312e`: `TasksHelper: The task %s does not exist.`
- `0x18003310b`: `TasksHelper: Verified that the task %s exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::TasksHelper::TaskExists(
        WaasMedic::TasksHelper *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  OLECHAR *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // r9d
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v16; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  OLECHAR *v19; // [rsp+88h] [rbp+38h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  const unsigned __int16 *v21; // [rsp+98h] [rbp+48h] BYREF

  v20 = 0;
  v6 = 0;
  v19 = 0;
  if ( a2 )
  {
    v6 = SysAllocString(a2);
    v19 = v6;
  }
  if ( a3 )
  {
    if ( *((_BYTE *)this + 17) )
    {
      *a3 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**((_QWORD **)this + 1) + 104LL))(
              *((_QWORD *)this + 1),
              v6,
              &v20);
      v7 = v10;
      if ( v10 < 0 )
      {
        if ( v10 == -2147024894 )
        {
          v7 = 0;
          *a3 = 0;
          LogLevelW(4u, L"TasksHelper: The task %s does not exist.", a2);
        }
        else
        {
          LogLevelW(2u, L"Failed to access task %s! hr = 0x%08x", a2, (unsigned int)v10);
          v11 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
          if ( *(_DWORD *)v11 > 5u
            && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
            && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
          {
            LODWORD(v19) = v7;
            v21 = a2;
            v16 = &gc_pszVersionString;
            v17 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v11,
              (unsigned int)&word_1800932BE,
              0,
              v12,
              (__int64)&v17,
              (__int64)&v16,
              (__int64)&v21,
              (__int64)&v19);
          }
        }
      }
      else
      {
        *a3 = 1;
        LogLevelW(4u, L"TasksHelper: Verified that the task %s exists.", a2);
      }
      SysFreeString(v6);
      v13 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    else
    {
      v7 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
        (const char *)0x8007139FLL,
        v15);
      SysFreeString(v6);
      v9 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  else
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x80004003LL,
      v15);
    SysFreeString(v6);
    v8 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003300c  push    rbp
0x18003300e  push    rbx
0x18003300f  push    rsi
0x180033010  push    rdi
0x180033011  push    r14
0x180033013  mov     rbp, rsp
0x180033016  sub     rsp, 50h
0x18003301a  mov     r14, r8
0x18003301d  mov     rsi, rdx
0x180033020  mov     rdi, rcx
0x180033023  mov     [rbp+arg_10], 0
0x18003302b  xor     ebx, ebx
0x18003302d  mov     [rbp+arg_8], rbx
0x180033031  test    rdx, rdx
0x180033034  jz      short loc_180033046
0x180033036  mov     rcx, rdx; psz
0x180033039  call    cs:__imp_SysAllocString
0x18003303f  mov     rbx, rax
0x180033042  mov     [rbp+arg_8], rax
0x180033046  test    r14, r14
0x180033049  jnz     short loc_180033092
0x18003304b  mov     rcx, [rbp+28h]; this
0x18003304f  mov     edi, 80004003h
0x180033054  mov     r9d, edi; char *
0x180033057  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003305e  mov     edx, 0AEh; void *
0x180033063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033068  nop
0x180033069  mov     rcx, rbx; bstrString
0x18003306c  call    cs:__imp_SysFreeString
0x180033072  nop
0x180033073  mov     rcx, [rbp+arg_10]
0x180033077  test    rcx, rcx
0x18003307a  jz      short loc_18003308D
0x18003307c  mov     [rbp+arg_10], r14
0x180033080  mov     rdx, [rcx]
0x180033083  mov     rax, [rdx+10h]
0x180033087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003308c  nop
0x18003308d  jmp     loc_1800331F0
0x180033092  cmp     byte ptr [rdi+11h], 0
0x180033096  jnz     short loc_1800330E3
0x180033098  mov     rcx, [rbp+28h]; this
0x18003309c  mov     edi, 8007139Fh
0x1800330a1  mov     r9d, edi; char *
0x1800330a4  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800330ab  mov     edx, 0AFh; void *
0x1800330b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330b5  nop
0x1800330b6  mov     rcx, rbx; bstrString
0x1800330b9  call    cs:__imp_SysFreeString
0x1800330bf  nop
0x1800330c0  mov     rcx, [rbp+arg_10]
0x1800330c4  test    rcx, rcx
0x1800330c7  jz      short loc_1800330DE
0x1800330c9  mov     [rbp+arg_10], 0
0x1800330d1  mov     rdx, [rcx]
0x1800330d4  mov     rax, [rdx+10h]
0x1800330d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330dd  nop
0x1800330de  jmp     loc_1800331F0
0x1800330e3  mov     byte ptr [r14], 0
0x1800330e7  mov     rcx, [rdi+8]
0x1800330eb  mov     rax, [rcx]
0x1800330ee  lea     r8, [rbp+arg_10]
0x1800330f2  mov     rdx, rbx
0x1800330f5  mov     rax, [rax+68h]
0x1800330f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330fe  mov     edi, eax
0x180033100  mov     r8, rsi
0x180033103  test    eax, eax
0x180033105  js      short loc_180033121
0x180033107  mov     byte ptr [r14], 1
0x18003310b  lea     rdx, aTaskshelperVer; "TasksHelper: Verified that the task %s "...
0x180033112  mov     ecx, 4; unsigned __int8
0x180033117  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003311c  jmp     loc_1800331C8
0x180033121  cmp     edi, 80070002h
0x180033127  jnz     short loc_180033137
0x180033129  xor     edi, edi
0x18003312b  mov     [r14], dil
0x18003312e  lea     rdx, aTaskshelperThe; "TasksHelper: The task %s does not exist"...
0x180033135  jmp     short loc_180033112
0x180033137  mov     r9d, edi
0x18003313a  lea     rdx, aFailedToAccess; "Failed to access task %s! hr = 0x%08x"
0x180033141  mov     ecx, 2; unsigned __int8
0x180033146  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003314b  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180033150  mov     rcx, [rax+8]
0x180033154  mov     eax, [rcx]
0x180033156  cmp     eax, 5
0x180033159  jbe     short loc_1800331C8
0x18003315b  mov     rdx, [rcx+18h]
0x18003315f  mov     rax, [rcx+10h]
0x180033163  mov     r8, 400000000000h
0x18003316d  test    r8, rax
0x180033170  jz      short loc_1800331C8
0x180033172  mov     rax, rdx
0x180033175  and     rax, r8
0x180033178  cmp     rax, rdx
0x18003317b  jnz     short loc_1800331C8
0x18003317d  mov     dword ptr [rbp+arg_8], edi
0x180033180  mov     [rbp+arg_18], rsi
0x180033184  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18003318b  mov     [rbp+var_10], rax
0x18003318f  mov     [rbp+var_8], 1000000h
0x180033197  lea     rax, [rbp+arg_8]
0x18003319b  mov     [rsp+50h+var_18], rax
0x1800331a0  lea     rax, [rbp+arg_18]
0x1800331a4  mov     [rsp+50h+var_20], rax
0x1800331a9  lea     rax, [rbp+var_10]
0x1800331ad  mov     [rsp+50h+var_28], rax
0x1800331b2  lea     rax, [rbp+var_8]
0x1800331b6  mov     [rsp+50h+var_30], rax
0x1800331bb  lea     rdx, word_1800932BE
0x1800331c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800331c7  nop
0x1800331c8  mov     rcx, rbx; bstrString
0x1800331cb  call    cs:__imp_SysFreeString
0x1800331d1  nop
0x1800331d2  mov     rcx, [rbp+arg_10]
0x1800331d6  test    rcx, rcx
0x1800331d9  jz      short loc_1800331F0
0x1800331db  mov     [rbp+arg_10], 0
0x1800331e3  mov     rax, [rcx]
0x1800331e6  mov     rax, [rax+10h]
0x1800331ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331ef  nop
0x1800331f0  mov     eax, edi
0x1800331f2  add     rsp, 50h
0x1800331f6  pop     r14
0x1800331f8  pop     rdi
0x1800331f9  pop     rsi
0x1800331fa  pop     rbx
0x1800331fb  pop     rbp
0x1800331fc  retn
```
