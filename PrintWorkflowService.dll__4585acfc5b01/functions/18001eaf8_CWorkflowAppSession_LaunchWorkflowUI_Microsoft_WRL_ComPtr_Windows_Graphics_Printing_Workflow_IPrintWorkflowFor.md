# CWorkflowAppSession::LaunchWorkflowUI(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001eaf8`
- end: `0x18001ecd0`
- name: `?LaunchWorkflowUI@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e9e0`

## callees

- `0x180002340`
- `0x180010b0c`
- `0x18001eaf8`
- `0x18001ecd8`
- `0x18001f200`
- `0x18005e010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ebc0`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ebe3`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ebc0`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18001ebe3`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18001ebd3`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18001ebd3`

## string_xrefs

- `0x18001eb59`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001eca2`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`

## pseudocode

```c
__int64 __fastcall CWorkflowAppSession::LaunchWorkflowUI(CWorkflowAppSession *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  unsigned __int8 v8; // bl
  __int64 (__fastcall *v9)(CWorkflowAppSession *, HWND *, HWND *, char *); // rax
  int v11; // edi
  __int64 v12; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 WindowThreadProcessId; // rcx
  DWORD v18; // eax
  HWND LastActivePopup; // rdi
  int v20; // ebx
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-50h]
  DWORD dwProcessId; // [rsp+40h] [rbp-30h] BYREF
  int v24; // [rsp+44h] [rbp-2Ch] BYREF
  int v25; // [rsp+48h] [rbp-28h] BYREF
  int v26; // [rsp+4Ch] [rbp-24h] BYREF
  int v27; // [rsp+50h] [rbp-20h] BYREF
  DWORD v28; // [rsp+54h] [rbp-1Ch] BYREF
  HWND hWnd; // [rsp+58h] [rbp-18h] BYREF
  HWND v30[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char v32; // [rsp+A0h] [rbp+30h] BYREF

  v4 = *(_QWORD *)this;
  v30[0] = 0;
  hWnd = 0;
  v8 = 1;
  v9 = *(__int64 (__fastcall **)(CWorkflowAppSession *, HWND *, HWND *, char *))(v4 + 56);
  v32 = 1;
  v11 = v9(this, v30, &hWnd, &v32);
  if ( v11 < 0 )
  {
    v12 = 344;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)v11,
      v22);
    return (unsigned int)v11;
  }
  if ( v32 )
    goto LABEL_20;
  v14 = *((_QWORD *)this + 6);
  v24 = 0;
  dwProcessId = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 128LL))(v14, &v24);
  if ( v11 < 0 )
  {
    v12 = 360;
    goto LABEL_3;
  }
  if ( !v24 )
  {
    WindowThreadProcessId = 0;
LABEL_13:
    v8 = 0;
    goto LABEL_15;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(hWnd, &dwProcessId);
  v18 = dwProcessId;
  if ( dwProcessId )
  {
    LastActivePopup = hWnd;
  }
  else
  {
    LastActivePopup = GetLastActivePopup(v30[0]);
    WindowThreadProcessId = GetWindowThreadProcessId(LastActivePopup, &dwProcessId);
    hWnd = LastActivePopup;
    v18 = dwProcessId;
  }
  if ( !v18 )
    goto LABEL_13;
  v30[0] = LastActivePopup;
LABEL_15:
  if ( (unsigned int)dword_180083038 > 5 )
  {
    v25 = v8;
    v26 = v24;
    v28 = dwProcessId;
    v27 = WindowThreadProcessId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      WindowThreadProcessId,
      (__int64)byte_180072111,
      v15,
      v16,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  if ( !v8 )
  {
    v20 = CWorkflowAppSession::LaunchWorkflowUIWithoutMem(
            (CWorkflowModalExperienceManagerAppListener **)this,
            a2,
            a3,
            a4);
    if ( v20 < 0 )
    {
      v21 = 418;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
        (const char *)(unsigned int)v20,
        v22);
      return (unsigned int)v20;
    }
    return 0;
  }
LABEL_20:
  v20 = CWorkflowAppSession::LaunchWorkflowUIWithMem(this, a3, a4);
  if ( v20 < 0 )
  {
    v21 = 410;
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x18001eaf8  mov     [rsp-28h+arg_8], rbx
0x18001eafd  mov     [rsp-28h+arg_10], rsi
0x18001eb02  push    rbp
0x18001eb03  push    rdi
0x18001eb04  push    r12
0x18001eb06  push    r14
0x18001eb08  push    r15
0x18001eb0a  mov     rbp, rsp
0x18001eb0d  sub     rsp, 70h
0x18001eb11  mov     rax, [rcx]
0x18001eb14  mov     r14, r9
0x18001eb17  mov     r15, r8
0x18001eb1a  mov     [rbp+var_10], 0
0x18001eb22  mov     r12, rdx
0x18001eb25  mov     [rbp+hWnd], 0
0x18001eb2d  mov     bl, 1
0x18001eb2f  lea     r9, [rbp+arg_0]
0x18001eb33  mov     rax, [rax+38h]
0x18001eb37  lea     r8, [rbp+hWnd]
0x18001eb3b  lea     rdx, [rbp+var_10]
0x18001eb3f  mov     [rbp+arg_0], bl
0x18001eb42  mov     rsi, rcx
0x18001eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb4a  mov     edi, eax
0x18001eb4c  test    eax, eax
0x18001eb4e  jns     short loc_18001EB6F
0x18001eb50  mov     edx, 158h; void *
0x18001eb55  mov     rcx, [rbp+28h]; this
0x18001eb59  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001eb60  mov     r9d, edi; char *
0x18001eb63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb68  mov     eax, edi
0x18001eb6a  jmp     loc_18001ECB7
0x18001eb6f  mov     r9b, [rbp+arg_0]
0x18001eb73  test    r9b, r9b
0x18001eb76  jnz     loc_18001EC7A
0x18001eb7c  mov     rcx, [rsi+30h]
0x18001eb80  lea     rdx, [rbp+var_2C]
0x18001eb84  mov     [rbp+var_2C], 0
0x18001eb8b  mov     [rbp+dwProcessId], 0
0x18001eb92  mov     rax, [rcx]
0x18001eb95  mov     rax, [rax+80h]
0x18001eb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba1  mov     edi, eax
0x18001eba3  test    eax, eax
0x18001eba5  jns     short loc_18001EBAE
0x18001eba7  mov     edx, 168h
0x18001ebac  jmp     short loc_18001EB55
0x18001ebae  cmp     [rbp+var_2C], 0
0x18001ebb2  jnz     short loc_18001EBB8
0x18001ebb4  xor     ecx, ecx
0x18001ebb6  jmp     short loc_18001EBFC
0x18001ebb8  mov     rcx, [rbp+hWnd]; hWnd
0x18001ebbc  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18001ebc0  call    cs:__imp_GetWindowThreadProcessId
0x18001ebc6  mov     ecx, eax
0x18001ebc8  mov     eax, [rbp+dwProcessId]
0x18001ebcb  test    eax, eax
0x18001ebcd  jnz     short loc_18001EBF4
0x18001ebcf  mov     rcx, [rbp+var_10]; hWnd
0x18001ebd3  call    cs:__imp_GetLastActivePopup
0x18001ebd9  mov     rcx, rax; hWnd
0x18001ebdc  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18001ebe0  mov     rdi, rax
0x18001ebe3  call    cs:__imp_GetWindowThreadProcessId
0x18001ebe9  mov     ecx, eax
0x18001ebeb  mov     [rbp+hWnd], rdi
0x18001ebef  mov     eax, [rbp+dwProcessId]
0x18001ebf2  jmp     short loc_18001EBF8
0x18001ebf4  mov     rdi, [rbp+hWnd]
0x18001ebf8  test    eax, eax
0x18001ebfa  jnz     short loc_18001EC00
0x18001ebfc  xor     bl, bl
0x18001ebfe  jmp     short loc_18001EC04
0x18001ec00  mov     [rbp+var_10], rdi
0x18001ec04  mov     eax, cs:dword_180083038
0x18001ec0a  cmp     eax, 5
0x18001ec0d  jbe     short loc_18001EC54
0x18001ec0f  movzx   eax, bl
0x18001ec12  lea     rdx, byte_180072111
0x18001ec19  mov     [rbp+var_28], eax
0x18001ec1c  mov     eax, [rbp+var_2C]
0x18001ec1f  mov     [rbp+var_24], eax
0x18001ec22  mov     eax, [rbp+dwProcessId]
0x18001ec25  mov     [rbp+var_1C], eax
0x18001ec28  lea     rax, [rbp+var_28]
0x18001ec2c  mov     [rsp+70h+var_38], rax
0x18001ec31  lea     rax, [rbp+var_24]
0x18001ec35  mov     [rsp+70h+var_40], rax
0x18001ec3a  lea     rax, [rbp+var_20]
0x18001ec3e  mov     [rsp+70h+var_48], rax
0x18001ec43  lea     rax, [rbp+var_1C]
0x18001ec47  mov     [rsp+70h+var_50], rax
0x18001ec4c  mov     [rbp+var_20], ecx
0x18001ec4f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ec54  test    bl, bl
0x18001ec56  jnz     short loc_18001EC76
0x18001ec58  mov     r9, r14
0x18001ec5b  mov     r8, r15
0x18001ec5e  mov     rdx, r12
0x18001ec61  mov     rcx, rsi; this
0x18001ec64  call    ?LaunchWorkflowUIWithoutMem@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CWorkflowAppSession::LaunchWorkflowUIWithoutMem(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,std::wstring const &,std::wstring const &)
0x18001ec69  mov     ebx, eax
0x18001ec6b  test    eax, eax
0x18001ec6d  jns     short loc_18001ECB5
0x18001ec6f  mov     edx, 1A2h
0x18001ec74  jmp     short loc_18001EC9E
0x18001ec76  mov     r9b, [rbp+arg_0]
0x18001ec7a  mov     r8, [rbp+var_10]
0x18001ec7e  mov     rdx, r12
0x18001ec81  mov     [rsp+70h+var_48], r14; __int64
0x18001ec86  mov     rcx, rsi; this
0x18001ec89  mov     [rsp+70h+var_50], r15; int
0x18001ec8e  call    ?LaunchWorkflowUIWithMem@CWorkflowAppSession@@QEAAJAEBV?$ComPtr@UIPrintWorkflowForegroundSession@Workflow@Printing@Graphics@Windows@@@WRL@Microsoft@@_KEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; CWorkflowAppSession::LaunchWorkflowUIWithMem(Microsoft::WRL::ComPtr<Windows::Graphics::Printing::Workflow::IPrintWorkflowForegroundSession> const &,unsigned __int64,uchar,std::wstring const &,std::wstring const &)
0x18001ec93  mov     ebx, eax
0x18001ec95  test    eax, eax
0x18001ec97  jns     short loc_18001ECB5
0x18001ec99  mov     edx, 19Ah; void *
0x18001ec9e  mov     rcx, [rbp+28h]; this
0x18001eca2  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001eca9  mov     r9d, ebx; char *
0x18001ecac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ecb1  mov     eax, ebx
0x18001ecb3  jmp     short loc_18001ECB7
0x18001ecb5  xor     eax, eax
0x18001ecb7  lea     r11, [rsp+70h+var_s0]
0x18001ecbc  mov     rbx, [r11+38h]
0x18001ecc0  mov     rsi, [r11+40h]
0x18001ecc4  mov     rsp, r11
0x18001ecc7  pop     r15
0x18001ecc9  pop     r14
0x18001eccb  pop     r12
0x18001eccd  pop     rdi
0x18001ecce  pop     rbp
0x18001eccf  retn
```
