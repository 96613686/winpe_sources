# Rdp::Avenc::Umrdp::CUmrdpProcessor::OpenPropertyStore(IPropertyStore * *)

- ea: `0x1800127a0`
- end: `0x180012947`
- name: `?OpenPropertyStore@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e848`
- `0x18000ec04`
- `0x1800127a0`
- `0x180015480`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001280a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800128db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001280a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800128db`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001286a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18001286a`

## string_xrefs

- `0x180012875`: `Failed to create property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::OpenPropertyStore(void **this, struct IPropertyStore **a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  struct IPropertyStore **v10; // rdi
  unsigned int v11; // eax
  struct IPropertyStore *v12; // rcx
  const char *v13; // r9
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-58h]
  const char *v20; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      (int)v20,
      10,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
        (const char *)0x80004003LL,
        v19);
    v10 = (struct IPropertyStore **)(this + 3);
    if ( !this[3] )
    {
      *v10 = 0;
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 3);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
        (const char *)v11,
        (int)"Failed to create property store",
        v20);
    }
    v12 = *v10;
    *a2 = *v10;
    ((void (__fastcall *)(struct IPropertyStore *))v12->lpVtbl->AddRef)(v12);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = GetCurrentThreadId();
      LOBYTE(v16) = v14;
      LOBYTE(v17) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        (int)v20,
        11,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4A,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800127a0  mov     [rsp+arg_0], rbx
0x1800127a5  mov     [rsp+arg_10], rsi
0x1800127aa  push    rdi
0x1800127ab  push    r12
0x1800127ad  push    r13
0x1800127af  push    r14
0x1800127b1  push    r15
0x1800127b3  sub     rsp, 50h
0x1800127b7  mov     r14, rdx
0x1800127ba  mov     r13, rcx
0x1800127bd  lea     r12, WPP_GLOBAL_Control
0x1800127c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800127cb  mov     bl, 1
0x1800127cd  cmp     rax, r12
0x1800127d0  jz      short loc_1800127E2
0x1800127d2  test    [rax+1Ch], bl
0x1800127d5  jz      short loc_1800127E2
0x1800127d7  cmp     byte ptr [rax+19h], 4
0x1800127db  jb      short loc_1800127E2
0x1800127dd  mov     dil, bl
0x1800127e0  jmp     short loc_1800127E5
0x1800127e2  xor     dil, dil
0x1800127e5  lea     rax, WPP_RECORDER_INITIALIZED
0x1800127ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800127f3  setnz   sil
0x1800127f7  test    dil, dil
0x1800127fa  jnz     short loc_18001280A
0x1800127fc  test    sil, sil
0x1800127ff  jnz     short loc_18001280A
0x180012801  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180012808  jmp     short loc_180012841
0x18001280a  call    cs:__imp_GetCurrentThreadId
0x180012810  mov     dword ptr [rsp+78h+var_38], eax; char
0x180012814  lea     r15, WPP_44e245a864023212cc554d824265b257_Traceguids
0x18001281b  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x180012820  mov     [rsp+78h+var_48], 0Ah; __int16
0x180012827  mov     rcx, cs:WPP_GLOBAL_Control
0x18001282e  mov     r9, [rcx+28h]; int
0x180012832  mov     r8b, sil; int
0x180012835  mov     dl, dil; int
0x180012838  mov     rcx, [rcx+10h]; int
0x18001283c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180012841  mov     rcx, [rsp+78h]; this
0x180012846  test    r14, r14
0x180012849  jz      loc_18001292F
0x18001284f  lea     rdi, [r13+18h]
0x180012853  cmp     qword ptr [rdi], 0
0x180012857  jnz     short loc_180012895
0x180012859  mov     qword ptr [rdi], 0
0x180012860  mov     rdx, rdi; ppv
0x180012863  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001286a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180012870  mov     rcx, [rsp+78h]; this
0x180012875  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x18001287c  mov     qword ptr [rsp+78h+var_58], rdx; int
0x180012881  mov     r9d, eax; char *
0x180012884  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001288b  mov     edx, 41h ; 'A'; void *
0x180012890  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012895  mov     rcx, [rdi]
0x180012898  mov     [r14], rcx
0x18001289b  mov     rax, [rcx]
0x18001289e  mov     rax, [rax+8]
0x1800128a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800128ae  cmp     rax, r12
0x1800128b1  jz      short loc_1800128BE
0x1800128b3  test    [rax+1Ch], bl
0x1800128b6  jz      short loc_1800128BE
0x1800128b8  cmp     byte ptr [rax+19h], 4
0x1800128bc  jnb     short loc_1800128C0
0x1800128be  xor     bl, bl
0x1800128c0  lea     rax, WPP_RECORDER_INITIALIZED
0x1800128c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800128ce  setnz   dil
0x1800128d2  test    bl, bl
0x1800128d4  jnz     short loc_1800128DB
0x1800128d6  test    dil, dil
0x1800128d9  jz      short loc_18001290A
0x1800128db  call    cs:__imp_GetCurrentThreadId
0x1800128e1  mov     dword ptr [rsp+78h+var_38], eax; char
0x1800128e5  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x1800128ea  mov     [rsp+78h+var_48], 0Bh; __int16
0x1800128f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128f8  mov     r9, [rcx+28h]; int
0x1800128fc  mov     r8b, dil; int
0x1800128ff  mov     dl, bl; int
0x180012901  mov     rcx, [rcx+10h]; int
0x180012905  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001290a  xor     eax, eax
0x18001290c  jmp     short loc_180012915
0x18001290e  mov     eax, [rsp+78h+arg_8]
0x180012915  lea     r11, [rsp+78h+var_28]
0x18001291a  mov     rbx, [r11+30h]
0x18001291e  mov     rsi, [r11+40h]
0x180012922  mov     rsp, r11
0x180012925  pop     r15
0x180012927  pop     r14
0x180012929  pop     r13
0x18001292b  pop     r12
0x18001292d  pop     rdi
0x18001292e  retn
0x18001292f  mov     r9d, 80004003h; char *
0x180012935  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001293c  lea     edx, [r14+36h]; void *
0x180012940  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
