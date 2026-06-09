# CFileIoChannel::OpenPropertyStore(IPropertyStore * *)

- ea: `0x180034520`
- end: `0x1800346db`
- name: `?OpenPropertyStore@CFileIoChannel@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18001dd50`
- `0x18001ddf4`
- `0x180034520`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003458a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003458a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034667`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800345f0`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800345f0`

## string_xrefs

- `0x180034601`: `Failed to create property store`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileIoChannel::OpenPropertyStore(void **this, struct IPropertyStore **a2)
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
      &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)0x80004003LL,
        v19);
    v10 = (struct IPropertyStore **)(this + 3);
    if ( !this[3] )
    {
      *v10 = 0;
      v11 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 3);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
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
        &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC7,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180034520  mov     [rsp+arg_0], rbx
0x180034525  mov     [rsp+arg_10], rsi
0x18003452a  push    rdi
0x18003452b  push    r12
0x18003452d  push    r13
0x18003452f  push    r14
0x180034531  push    r15
0x180034533  sub     rsp, 50h
0x180034537  mov     r14, rdx
0x18003453a  mov     r13, rcx
0x18003453d  lea     r12, WPP_GLOBAL_Control
0x180034544  mov     rax, cs:WPP_GLOBAL_Control
0x18003454b  mov     bl, 1
0x18003454d  cmp     rax, r12
0x180034550  jz      short loc_180034562
0x180034552  test    [rax+1Ch], bl
0x180034555  jz      short loc_180034562
0x180034557  cmp     byte ptr [rax+19h], 4
0x18003455b  jb      short loc_180034562
0x18003455d  mov     dil, bl
0x180034560  jmp     short loc_180034565
0x180034562  xor     dil, dil
0x180034565  lea     rax, WPP_RECORDER_INITIALIZED
0x18003456c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180034573  setnz   sil
0x180034577  test    dil, dil
0x18003457a  jnz     short loc_18003458A
0x18003457c  test    sil, sil
0x18003457f  jnz     short loc_18003458A
0x180034581  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x180034588  jmp     short loc_1800345C7
0x18003458a  call    cs:__imp_GetCurrentThreadId
0x180034591  nop     dword ptr [rax+rax+00h]
0x180034596  mov     dword ptr [rsp+78h+var_38], eax; char
0x18003459a  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x1800345a1  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x1800345a6  mov     [rsp+78h+var_48], 0Ah; __int16
0x1800345ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345b4  mov     r9, [rcx+28h]; int
0x1800345b8  mov     r8b, sil; int
0x1800345bb  mov     dl, dil; int
0x1800345be  mov     rcx, [rcx+10h]; int
0x1800345c2  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800345c7  mov     rcx, [rsp+78h]; this
0x1800345cc  test    r14, r14
0x1800345cf  jz      loc_1800346C2
0x1800345d5  lea     rdi, [r13+18h]
0x1800345d9  cmp     qword ptr [rdi], 0
0x1800345dd  jnz     short loc_180034621
0x1800345df  mov     qword ptr [rdi], 0
0x1800345e6  mov     rdx, rdi; ppv
0x1800345e9  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800345f0  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800345f7  nop     dword ptr [rax+rax+00h]
0x1800345fc  mov     rcx, [rsp+78h]; this
0x180034601  lea     rdx, aFailedToCreate_8; "Failed to create property store"
0x180034608  mov     qword ptr [rsp+78h+var_58], rdx; int
0x18003460d  mov     r9d, eax; char *
0x180034610  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180034617  mov     edx, 0BEh; void *
0x18003461c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034621  mov     rcx, [rdi]
0x180034624  mov     [r14], rcx
0x180034627  mov     rax, [rcx]
0x18003462a  mov     rax, [rax+8]
0x18003462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034633  mov     rax, cs:WPP_GLOBAL_Control
0x18003463a  cmp     rax, r12
0x18003463d  jz      short loc_18003464A
0x18003463f  test    [rax+1Ch], bl
0x180034642  jz      short loc_18003464A
0x180034644  cmp     byte ptr [rax+19h], 4
0x180034648  jnb     short loc_18003464C
0x18003464a  xor     bl, bl
0x18003464c  lea     rax, WPP_RECORDER_INITIALIZED
0x180034653  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003465a  setnz   dil
0x18003465e  test    bl, bl
0x180034660  jnz     short loc_180034667
0x180034662  test    dil, dil
0x180034665  jz      short loc_18003469C
0x180034667  call    cs:__imp_GetCurrentThreadId
0x18003466e  nop     dword ptr [rax+rax+00h]
0x180034673  mov     dword ptr [rsp+78h+var_38], eax; char
0x180034677  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x18003467c  mov     [rsp+78h+var_48], 0Bh; __int16
0x180034683  mov     rcx, cs:WPP_GLOBAL_Control
0x18003468a  mov     r9, [rcx+28h]; int
0x18003468e  mov     r8b, dil; int
0x180034691  mov     dl, bl; int
0x180034693  mov     rcx, [rcx+10h]; int
0x180034697  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003469c  xor     eax, eax
0x18003469e  jmp     short loc_1800346A7
0x1800346a0  mov     eax, [rsp+78h+arg_8]
0x1800346a7  lea     r11, [rsp+78h+var_28]
0x1800346ac  mov     rbx, [r11+30h]
0x1800346b0  mov     rsi, [r11+40h]
0x1800346b4  mov     rsp, r11
0x1800346b7  pop     r15
0x1800346b9  pop     r14
0x1800346bb  pop     r13
0x1800346bd  pop     r12
0x1800346bf  pop     rdi
0x1800346c0  retn
0x1800346c2  mov     r9d, 80004003h; char *
0x1800346c8  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800346cf  mov     edx, 0B3h; void *
0x1800346d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
