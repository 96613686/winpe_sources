# WaasMedic::TasksHelper::TaskExists(ushort const *,bool *)

- ea: `0x180060440`
- end: `0x180060630`
- name: `?TaskExists@TasksHelper@WaasMedic@@QEAAJPEBGPEA_N@Z`
- size: `496`
- prototype: `int(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180054fd0`
- `0x18005acb8`

## callees

- `0x1800023b0`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180060440`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006046d`
- `OLEAUT32!__imp_SysAllocString` at `0x18006046d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800604a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800604ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800605fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800604a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800604ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800605fe`

## string_xrefs

- `0x18006048b`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x1800604d8`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18006056e`: `Failed to access task %s! hr = 0x%08x`
- `0x18006053f`: `TasksHelper: Verified that the task %s exists.`
- `0x180060562`: `TasksHelper: The task %s does not exist.`

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
  const struct _tlgProvider_t *v11; // rax
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
          v11 = WaasMedic::TelemetryProvider::Provider();
          if ( *(_DWORD *)v11 > 5u
            && (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v11 + 3) & 0x400000000000LL) == *((_QWORD *)v11 + 3) )
          {
            LODWORD(v19) = v7;
            v21 = a2;
            v16 = &gc_pszVersionString;
            v17 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v11,
              (unsigned int)&dword_18008A60C,
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
0x180060440  push    rbp
0x180060442  push    rbx
0x180060443  push    rsi
0x180060444  push    rdi
0x180060445  push    r14
0x180060447  mov     rbp, rsp
0x18006044a  sub     rsp, 50h
0x18006044e  mov     r14, r8
0x180060451  mov     rsi, rdx
0x180060454  mov     rdi, rcx
0x180060457  mov     [rbp+arg_10], 0
0x18006045f  xor     ebx, ebx
0x180060461  mov     [rbp+arg_8], rbx
0x180060465  test    rdx, rdx
0x180060468  jz      short loc_18006047A
0x18006046a  mov     rcx, rdx; psz
0x18006046d  call    cs:__imp_SysAllocString
0x180060473  mov     rbx, rax
0x180060476  mov     [rbp+arg_8], rax
0x18006047a  test    r14, r14
0x18006047d  jnz     short loc_1800604C6
0x18006047f  mov     rcx, [rbp+28h]; this
0x180060483  mov     edi, 80004003h
0x180060488  mov     r9d, edi; char *
0x18006048b  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180060492  mov     edx, 0AEh; void *
0x180060497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006049c  nop
0x18006049d  mov     rcx, rbx; bstrString
0x1800604a0  call    cs:__imp_SysFreeString
0x1800604a6  nop
0x1800604a7  mov     rcx, [rbp+arg_10]
0x1800604ab  test    rcx, rcx
0x1800604ae  jz      short loc_1800604C1
0x1800604b0  mov     [rbp+arg_10], r14
0x1800604b4  mov     rdx, [rcx]
0x1800604b7  mov     rax, [rdx+10h]
0x1800604bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604c0  nop
0x1800604c1  jmp     loc_180060623
0x1800604c6  cmp     byte ptr [rdi+11h], 0
0x1800604ca  jnz     short loc_180060517
0x1800604cc  mov     rcx, [rbp+28h]; this
0x1800604d0  mov     edi, 8007139Fh
0x1800604d5  mov     r9d, edi; char *
0x1800604d8  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800604df  mov     edx, 0AFh; void *
0x1800604e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800604e9  nop
0x1800604ea  mov     rcx, rbx; bstrString
0x1800604ed  call    cs:__imp_SysFreeString
0x1800604f3  nop
0x1800604f4  mov     rcx, [rbp+arg_10]
0x1800604f8  test    rcx, rcx
0x1800604fb  jz      short loc_180060512
0x1800604fd  mov     [rbp+arg_10], 0
0x180060505  mov     rdx, [rcx]
0x180060508  mov     rax, [rdx+10h]
0x18006050c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060511  nop
0x180060512  jmp     loc_180060623
0x180060517  mov     byte ptr [r14], 0
0x18006051b  mov     rcx, [rdi+8]
0x18006051f  mov     rax, [rcx]
0x180060522  lea     r8, [rbp+arg_10]
0x180060526  mov     rdx, rbx
0x180060529  mov     rax, [rax+68h]
0x18006052d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060532  mov     edi, eax
0x180060534  mov     r8, rsi
0x180060537  test    eax, eax
0x180060539  js      short loc_180060555
0x18006053b  mov     byte ptr [r14], 1
0x18006053f  lea     rdx, aTaskshelperVer; "TasksHelper: Verified that the task %s "...
0x180060546  mov     ecx, 4; unsigned __int8
0x18006054b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180060550  jmp     loc_1800605FB
0x180060555  cmp     edi, 80070002h
0x18006055b  jnz     short loc_18006056B
0x18006055d  xor     edi, edi
0x18006055f  mov     [r14], dil
0x180060562  lea     rdx, aTaskshelperThe; "TasksHelper: The task %s does not exist"...
0x180060569  jmp     short loc_180060546
0x18006056b  mov     r9d, edi
0x18006056e  lea     rdx, aFailedToAccess; "Failed to access task %s! hr = 0x%08x"
0x180060575  mov     ecx, 2; unsigned __int8
0x18006057a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006057f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180060584  mov     ecx, [rax]
0x180060586  cmp     ecx, 5
0x180060589  jbe     short loc_1800605FB
0x18006058b  mov     rdx, [rax+18h]
0x18006058f  mov     rcx, [rax+10h]
0x180060593  mov     r8, 400000000000h
0x18006059d  test    r8, rcx
0x1800605a0  jz      short loc_1800605FB
0x1800605a2  mov     rcx, rdx
0x1800605a5  and     rcx, r8
0x1800605a8  cmp     rcx, rdx
0x1800605ab  jnz     short loc_1800605FB
0x1800605ad  mov     dword ptr [rbp+arg_8], edi
0x1800605b0  mov     [rbp+arg_18], rsi
0x1800605b4  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800605bb  mov     [rbp+var_10], rcx
0x1800605bf  mov     [rbp+var_8], 1000000h
0x1800605c7  lea     rcx, [rbp+arg_8]
0x1800605cb  mov     [rsp+50h+var_18], rcx
0x1800605d0  lea     rcx, [rbp+arg_18]
0x1800605d4  mov     [rsp+50h+var_20], rcx
0x1800605d9  lea     rcx, [rbp+var_10]
0x1800605dd  mov     [rsp+50h+var_28], rcx
0x1800605e2  lea     rcx, [rbp+var_8]
0x1800605e6  mov     [rsp+50h+var_30], rcx
0x1800605eb  lea     rdx, dword_18008A60C
0x1800605f2  mov     rcx, rax
0x1800605f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800605fa  nop
0x1800605fb  mov     rcx, rbx; bstrString
0x1800605fe  call    cs:__imp_SysFreeString
0x180060604  nop
0x180060605  mov     rcx, [rbp+arg_10]
0x180060609  test    rcx, rcx
0x18006060c  jz      short loc_180060623
0x18006060e  mov     [rbp+arg_10], 0
0x180060616  mov     rax, [rcx]
0x180060619  mov     rax, [rax+10h]
0x18006061d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060622  nop
0x180060623  mov     eax, edi
0x180060625  add     rsp, 50h
0x180060629  pop     r14
0x18006062b  pop     rdi
0x18006062c  pop     rsi
0x18006062d  pop     rbx
0x18006062e  pop     rbp
0x18006062f  retn
```
