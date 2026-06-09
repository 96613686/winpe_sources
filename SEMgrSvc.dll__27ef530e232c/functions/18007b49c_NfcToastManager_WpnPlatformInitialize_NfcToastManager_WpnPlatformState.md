# NfcToastManager::WpnPlatformInitialize(NfcToastManager::WpnPlatformState *)

- ea: `0x18007b49c`
- end: `0x18007b72b`
- name: `?WpnPlatformInitialize@NfcToastManager@@AEAAJPEAUWpnPlatformState@1@@Z`
- size: `655`
- prototype: `__int64 __fastcall(NfcToastManager *__hidden this, struct NfcToastManager::WpnPlatformState *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a6f0`
- `0x18007b06c`

## callees

- `0x18000c964`
- `0x18007ae54`
- `0x18007aec4`
- `0x18007b49c`
- `0x18007b7f4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b5cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007b5cb`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18007b58a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18007b58a`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18007b59d`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18007b59d`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18007b621`
- `combase!__imp_CoCreateInstanceAsUser` at `0x18007b621`

## string_xrefs

- `0x18007b66f`: `onecoreuap\ds\nfc\product\semanagement\common\nfctoast\lib\nfctoastmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NfcToastManager::WpnPlatformInitialize(
        NfcToastManager *this,
        struct NfcToastManager::WpnPlatformState *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rcx
  bool v11; // di
  GUID *v12; // rcx
  HRESULT InstanceAsUser; // eax
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int DefaultUserContextToken; // eax
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, __int128 *); // rsi
  __int64 v20; // rcx
  int v21; // eax
  LPVOID v22; // rdi
  __int64 (__fastcall *v23)(LPVOID, char *); // rsi
  __int64 v24; // rcx
  GUID *ppv; // [rsp+20h] [rbp-30h]
  LPVOID v26; // [rsp+30h] [rbp-20h] BYREF
  __int128 v27; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v29; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int64 v30; // [rsp+80h] [rbp+30h] BYREF

  if ( !*((_BYTE *)this + 24) )
  {
    v27 = 0;
    v26 = 0;
    v29 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v29, 0);
    v11 = (unsigned int)(v29 - 7) <= 1;
    if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() || v11 )
    {
      v30 = 0;
      DefaultUserContextToken = _GetDefaultUserContextToken(&v30);
      v12 = &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c;
      if ( DefaultUserContextToken >= 0 )
      {
        ppv = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
        InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, v30);
LABEL_22:
        v14 = InstanceAsUser;
        if ( InstanceAsUser >= 0 )
        {
          v18 = v26;
          v19 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v26 + 24LL);
          v20 = v27;
          if ( (_QWORD)v27 )
          {
            *(_QWORD *)&v27 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          v21 = v19(v18, &v27);
          v14 = v21;
          if ( v21 >= 0 )
          {
            v22 = v26;
            v23 = *(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v26 + 40LL);
            v24 = *((_QWORD *)&v27 + 1);
            if ( *((_QWORD *)&v27 + 1) )
            {
              *((_QWORD *)&v27 + 1) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
            v21 = v23(v22, (char *)&v27 + 8);
            v14 = v21;
            if ( v21 >= 0 )
            {
              LODWORD(ppv) = 0x40000000;
              v21 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64))(**((_QWORD **)&v27 + 1)
                                                                                                 + 24LL))(
                      *((_QWORD *)&v27 + 1),
                      L"System",
                      L"Windows.SystemToast.SEManagement",
                      133693439);
              v14 = v21;
              if ( v21 >= 0 )
              {
                NfcToastManager::WpnPlatformState::operator=(a2, &v26);
                v14 = 0;
                goto LABEL_39;
              }
              v16 = 71;
            }
            else
            {
              v16 = 69;
            }
          }
          else
          {
            v16 = 66;
          }
          v15 = (unsigned int)v21;
        }
        else
        {
          v15 = (unsigned int)InstanceAsUser;
          v16 = 62;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\nfctoast\\lib\\nfctoastmanager.cpp",
          (const char *)v15,
          (int)ppv);
LABEL_39:
        NfcToastManager::WpnPlatformState::~WpnPlatformState((NfcToastManager::WpnPlatformState *)&v26);
        return v14;
      }
    }
    else
    {
      v12 = &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9;
    }
    InstanceAsUser = CoCreateInstance(v12, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v26);
    goto LABEL_22;
  }
  v4 = *((_QWORD *)this + 4);
  if ( *(_QWORD *)a2 != v4 )
  {
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*((_QWORD *)this + 4));
    v5 = *(_QWORD *)a2;
    *(_QWORD *)a2 = v4;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 5);
  if ( *((_QWORD *)a2 + 1) != v6 )
  {
    if ( v6 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*((_QWORD *)this + 5));
    v7 = *((_QWORD *)a2 + 1);
    *((_QWORD *)a2 + 1) = v6;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 6);
  if ( *((_QWORD *)a2 + 2) != v8 )
  {
    if ( v8 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 6));
    v9 = *((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 2) = v8;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18007b49c  mov     [rsp-18h+arg_8], rbx
0x18007b4a1  push    rbp
0x18007b4a2  push    rsi
0x18007b4a3  push    rdi
0x18007b4a4  mov     rbp, rsp
0x18007b4a7  sub     rsp, 50h
0x18007b4ab  mov     rbx, rdx
0x18007b4ae  mov     rsi, rcx
0x18007b4b1  cmp     byte ptr [rcx+18h], 0
0x18007b4b5  jz      loc_18007B56A
0x18007b4bb  mov     rdi, [rcx+20h]
0x18007b4bf  cmp     [rdx], rdi
0x18007b4c2  jz      short loc_18007B4F1
0x18007b4c4  test    rdi, rdi
0x18007b4c7  jz      short loc_18007B4D9
0x18007b4c9  mov     rax, [rdi]
0x18007b4cc  mov     rcx, rdi
0x18007b4cf  mov     rax, [rax+8]
0x18007b4d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4d8  nop
0x18007b4d9  mov     rcx, [rbx]
0x18007b4dc  mov     [rbx], rdi
0x18007b4df  test    rcx, rcx
0x18007b4e2  jz      short loc_18007B4F1
0x18007b4e4  mov     rax, [rcx]
0x18007b4e7  mov     rax, [rax+10h]
0x18007b4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4f0  nop
0x18007b4f1  mov     rdi, [rsi+28h]
0x18007b4f5  cmp     [rbx+8], rdi
0x18007b4f9  jz      short loc_18007B52A
0x18007b4fb  test    rdi, rdi
0x18007b4fe  jz      short loc_18007B510
0x18007b500  mov     rax, [rdi]
0x18007b503  mov     rcx, rdi
0x18007b506  mov     rax, [rax+8]
0x18007b50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b50f  nop
0x18007b510  mov     rcx, [rbx+8]
0x18007b514  mov     [rbx+8], rdi
0x18007b518  test    rcx, rcx
0x18007b51b  jz      short loc_18007B52A
0x18007b51d  mov     rax, [rcx]
0x18007b520  mov     rax, [rax+10h]
0x18007b524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b529  nop
0x18007b52a  mov     rdi, [rsi+30h]
0x18007b52e  cmp     [rbx+10h], rdi
0x18007b532  jz      short loc_18007B563
0x18007b534  test    rdi, rdi
0x18007b537  jz      short loc_18007B549
0x18007b539  mov     rax, [rdi]
0x18007b53c  mov     rcx, rdi
0x18007b53f  mov     rax, [rax+8]
0x18007b543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b548  nop
0x18007b549  mov     rcx, [rbx+10h]
0x18007b54d  mov     [rbx+10h], rdi
0x18007b551  test    rcx, rcx
0x18007b554  jz      short loc_18007B563
0x18007b556  mov     rax, [rcx]
0x18007b559  mov     rax, [rax+10h]
0x18007b55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b562  nop
0x18007b563  xor     eax, eax
0x18007b565  jmp     loc_18007B71E
0x18007b56a  xorps   xmm0, xmm0
0x18007b56d  movdqu  [rbp+var_18], xmm0
0x18007b572  mov     [rbp+var_20], 0
0x18007b57a  mov     [rbp+arg_0], 0
0x18007b581  xor     r8d, r8d
0x18007b584  lea     rdx, [rbp+arg_0]
0x18007b588  xor     ecx, ecx
0x18007b58a  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18007b590  mov     eax, [rbp+arg_0]
0x18007b593  add     eax, 0FFFFFFF9h
0x18007b596  cmp     eax, 1
0x18007b599  setbe   dil
0x18007b59d  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18007b5a3  test    al, al
0x18007b5a5  jnz     short loc_18007B5E4
0x18007b5a7  test    dil, dil
0x18007b5aa  jnz     short loc_18007B5E4
0x18007b5ac  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x18007b5b3  lea     rax, [rbp+var_20]
0x18007b5b7  mov     [rsp+50h+ppv], rax; int
0x18007b5bc  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18007b5c3  mov     r8d, 404h; dwClsContext
0x18007b5c9  xor     edx, edx; pUnkOuter
0x18007b5cb  call    cs:__imp_CoCreateInstance
0x18007b5d1  mov     edi, eax
0x18007b5d3  test    eax, eax
0x18007b5d5  jns     short loc_18007B629
0x18007b5d7  mov     r9d, eax
0x18007b5da  mov     edx, 3Eh ; '>'
0x18007b5df  jmp     loc_18007B66F
0x18007b5e4  mov     [rbp+arg_10], 0
0x18007b5ec  lea     rcx, [rbp+arg_10]; unsigned __int64 *
0x18007b5f0  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x18007b5f5  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x18007b5fc  test    eax, eax
0x18007b5fe  js      short loc_18007B5B3
0x18007b600  lea     rax, [rbp+var_20]
0x18007b604  mov     [rsp+50h+var_28], rax
0x18007b609  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x18007b610  mov     [rsp+50h+ppv], r9
0x18007b615  mov     r9, [rbp+arg_10]
0x18007b619  xor     edx, edx
0x18007b61b  mov     r8d, 404h
0x18007b621  call    cs:__imp_CoCreateInstanceAsUser
0x18007b627  jmp     short loc_18007B5D1
0x18007b629  mov     rdi, [rbp+var_20]
0x18007b62d  mov     rax, [rdi]
0x18007b630  mov     rsi, [rax+18h]
0x18007b634  mov     rcx, qword ptr [rbp+var_18]
0x18007b638  test    rcx, rcx
0x18007b63b  jz      short loc_18007B652
0x18007b63d  mov     qword ptr [rbp+var_18], 0
0x18007b645  mov     rdx, [rcx]
0x18007b648  mov     rax, [rdx+10h]
0x18007b64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b651  nop
0x18007b652  lea     rdx, [rbp+var_18]
0x18007b656  mov     rcx, rdi
0x18007b659  mov     rax, rsi
0x18007b65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b661  mov     edi, eax
0x18007b663  test    eax, eax
0x18007b665  jns     short loc_18007B684
0x18007b667  mov     edx, 42h ; 'B'; void *
0x18007b66c  mov     r9d, eax; char *
0x18007b66f  lea     r8, aOnecoreuapDsNf_58; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18007b676  mov     rcx, [rbp+18h]; this
0x18007b67a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b67f  jmp     loc_18007B713
0x18007b684  mov     rdi, [rbp+var_20]
0x18007b688  mov     rax, [rdi]
0x18007b68b  mov     rsi, [rax+28h]
0x18007b68f  mov     rcx, qword ptr [rbp+var_18+8]
0x18007b693  test    rcx, rcx
0x18007b696  jz      short loc_18007B6AD
0x18007b698  mov     qword ptr [rbp+var_18+8], 0
0x18007b6a0  mov     rdx, [rcx]
0x18007b6a3  mov     rax, [rdx+10h]
0x18007b6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6ac  nop
0x18007b6ad  lea     rdx, [rbp+var_18+8]
0x18007b6b1  mov     rcx, rdi
0x18007b6b4  mov     rax, rsi
0x18007b6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6bc  mov     edi, eax
0x18007b6be  test    eax, eax
0x18007b6c0  jns     short loc_18007B6C9
0x18007b6c2  mov     edx, 45h ; 'E'
0x18007b6c7  jmp     short loc_18007B66C
0x18007b6c9  mov     rcx, qword ptr [rbp+var_18+8]
0x18007b6cd  mov     rax, [rcx]
0x18007b6d0  mov     dword ptr [rsp+50h+ppv], 40000000h
0x18007b6d8  mov     r9d, 7F7FFFFh
0x18007b6de  lea     r8, aWindowsSystemt; "Windows.SystemToast.SEManagement"
0x18007b6e5  lea     rdx, aSystem; "System"
0x18007b6ec  mov     rax, [rax+18h]
0x18007b6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6f5  mov     edi, eax
0x18007b6f7  test    eax, eax
0x18007b6f9  jns     short loc_18007B705
0x18007b6fb  mov     edx, 47h ; 'G'
0x18007b700  jmp     loc_18007B66C
0x18007b705  lea     rdx, [rbp+var_20]
0x18007b709  mov     rcx, rbx
0x18007b70c  call    ??4WpnPlatformState@NfcToastManager@@QEAAAEAU01@$$QEAU01@@Z; NfcToastManager::WpnPlatformState::operator=(NfcToastManager::WpnPlatformState &&)
0x18007b711  xor     edi, edi
0x18007b713  lea     rcx, [rbp+var_20]; this
0x18007b717  call    ??1WpnPlatformState@NfcToastManager@@QEAA@XZ; NfcToastManager::WpnPlatformState::~WpnPlatformState(void)
0x18007b71c  mov     eax, edi
0x18007b71e  mov     rbx, [rsp+50h+arg_8]
0x18007b723  add     rsp, 50h
0x18007b727  pop     rdi
0x18007b728  pop     rsi
0x18007b729  pop     rbp
0x18007b72a  retn
```
