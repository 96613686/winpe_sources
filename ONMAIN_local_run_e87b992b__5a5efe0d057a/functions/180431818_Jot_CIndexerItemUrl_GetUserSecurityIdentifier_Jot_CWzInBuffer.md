# Jot::CIndexerItemUrl::GetUserSecurityIdentifier(Jot::CWzInBuffer &)

- ea: `0x180431818`
- end: `0x180431a97`
- name: `?GetUserSecurityIdentifier@CIndexerItemUrl@Jot@@CA_NAEAVCWzInBuffer@2@@Z`
- size: `639`
- prototype: `bool __fastcall(struct Jot::CWzInBuffer *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180431604`
- `0x180589328`

## callees

- `0x18005ccc0`
- `0x180148a20`
- `0x18014a0d0`
- `0x18014f4d0`
- `0x1802e3f10`
- `0x1802e5060`
- `0x1802e5190`
- `0x18033d2b0`
- `0x180431818`
- `0x180701de0`
- `0x180a6e9f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1804319cc`
- `KERNEL32!CloseHandle` at `0x1804319e1`
- `KERNEL32!CloseHandle` at `0x180431a8b`
- `KERNEL32!CloseHandle` at `0x1804319cc`
- `KERNEL32!CloseHandle` at `0x1804319e1`
- `KERNEL32!CloseHandle` at `0x180431a8b`
- `KERNEL32!GetLastError` at `0x1804318f1`
- `KERNEL32!GetLastError` at `0x1804318f1`
- `KERNEL32!GetCurrentProcess` at `0x18043188e`
- `KERNEL32!GetCurrentProcess` at `0x18043188e`
- `KERNEL32!LocalFree` at `0x180431a61`
- `KERNEL32!LocalFree` at `0x180431a61`
- `MSVCP140!_Mtx_unlock` at `0x180431876`
- `MSVCP140!_Mtx_unlock` at `0x1804318c3`
- `MSVCP140!_Mtx_unlock` at `0x180431876`
- `MSVCP140!_Mtx_unlock` at `0x1804318c3`
- `ADVAPI32!OpenProcessToken` at `0x1804318a0`
- `ADVAPI32!OpenProcessToken` at `0x1804318a0`
- `ADVAPI32!GetTokenInformation` at `0x1804318eb`
- `ADVAPI32!GetTokenInformation` at `0x18043196f`
- `ADVAPI32!GetTokenInformation` at `0x1804318eb`
- `ADVAPI32!GetTokenInformation` at `0x18043196f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180431990`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180431990`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804319a1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804319b7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180431a73`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804319a1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804319b7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180431a73`

## pseudocode

```c
bool __fastcall Jot::CIndexerItemUrl::GetUserSecurityIdentifier(struct Jot::CWzInBuffer *this)
{
  const wchar_t *v2; // rax
  bool v3; // bl
  HANDLE CurrentProcess; // rax
  __int64 v6; // r9
  void ****v7; // r8
  DWORD v8; // edx
  DWORD v9; // ebx
  void *v10; // rdx
  PSID *v11; // rcx
  void *v12; // rdx
  unsigned int v13; // r8d
  void *v14; // rax
  Jot::CWzInBuffer *v15; // rbx
  Jot::CWzInBuffer *v16; // rcx
  void *v17; // rdx
  _QWORD v18[2]; // [rsp+38h] [rbp-38h] BYREF
  void ****v19; // [rsp+48h] [rbp-28h]
  DWORD v20; // [rsp+50h] [rbp-20h]
  void ***v21; // [rsp+58h] [rbp-18h] BYREF
  Mso::Memory *v22; // [rsp+60h] [rbp-10h]
  int v23; // [rsp+68h] [rbp-8h]
  DWORD TokenInformationLength; // [rsp+98h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+A0h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp+38h] BYREF

  v18[0] = &Jot::CIndexerItemUrl::s_xData;
  MsoCF::CMsoCfCriticalSectionObject::lock((MsoCF::CMsoCfCriticalSectionObject *)qword_1814ED808);
  v18[1] = &Jot::CIndexerItemUrl::s_xData;
  if ( Jot::CIndexerItemUrl::s_xData )
  {
LABEL_2:
    v2 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(Jot::CIndexerItemUrl::s_xData);
    Jot::CWzInBuffer::CopyWz(this, v2);
    v3 = !Jot::CWzInBuffer::IsEmpty(this);
    _Mtx_unlock((_Mtx_t)qword_1814ED808);
    return v3;
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_4;
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
LABEL_15:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    MsoCF::CXPtr<Jot::CWinFileProxyBase *,MsoCF::CExclusive<Jot::CWinFileProxyBase *>>::~CXPtr<Jot::CWinFileProxyBase *,MsoCF::CExclusive<Jot::CWinFileProxyBase *>>(v18);
    return 0;
  }
  v7 = &v21;
  v19 = &v21;
  v20 = 0;
  v21 = &off_181515648;
  v22 = 0;
  v23 = 0;
  v8 = TokenInformationLength;
  v9 = TokenInformationLength;
  if ( (int)TokenInformationLength > 0 )
  {
    LOBYTE(v6) = 1;
    ((void (__fastcall *)(void ***, void ****, _QWORD, __int64))*off_181515648)(
      &off_181515648,
      &v21,
      TokenInformationLength,
      v6);
    v8 = TokenInformationLength;
    v7 = v19;
  }
  v20 = v9;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v7[1], v8, &TokenInformationLength) )
  {
    v20 = 0;
    Mso::Memory::Free(v22, v10);
    goto LABEL_15;
  }
  v11 = (PSID *)v19[1];
  StringSid = 0;
  if ( ConvertSidToStringSidW(*v11, &StringSid) )
  {
    v14 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x58, (unsigned __int64)v12, v13);
    if ( v14 )
      v15 = (Jot::CWzInBuffer *)Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>(v14);
    else
      v15 = 0;
    v16 = Jot::CIndexerItemUrl::s_xData;
    if ( Jot::CIndexerItemUrl::s_xData != v15 )
    {
      if ( Jot::CIndexerItemUrl::s_xData )
        Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::`scalar deleting destructor'(Jot::CIndexerItemUrl::s_xData);
      Jot::CIndexerItemUrl::s_xData = v15;
      v16 = v15;
    }
    Jot::CWzInBuffer::CopyWz(v16, L"{");
    Jot::CWzInBuffer::AppendWz(Jot::CIndexerItemUrl::s_xData, StringSid);
    Jot::CWzInBuffer::AppendWz(Jot::CIndexerItemUrl::s_xData, L"}");
    LocalFree(StringSid);
    v20 = 0;
    Mso::Memory::Free(v22, v17);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    goto LABEL_2;
  }
  v20 = 0;
  Mso::Memory::Free(v22, v12);
LABEL_4:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  _Mtx_unlock((_Mtx_t)qword_1814ED808);
  return 0;
}

```

## disassembly

```asm
0x180431818  push    rbp
0x18043181a  push    rbx
0x18043181b  push    rdi
0x18043181c  mov     rbp, rsp
0x18043181f  sub     rsp, 70h
0x180431823  mov     rdi, rcx
0x180431826  lea     rbx, ?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A; MsoCF::CExclusive<Jot::CIndexerItemUrl::GlobalCacheData> Jot::CIndexerItemUrl::s_xData
0x18043182d  mov     [rbp+var_38], rbx
0x180431831  lea     rcx, qword_1814ED808; this
0x180431838  call    ?lock@CMsoCfCriticalSectionObject@MsoCF@@QEAAXXZ; MsoCF::CMsoCfCriticalSectionObject::lock(void)
0x18043183d  mov     [rbp+var_30], rbx
0x180431841  cmp     cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A, 0; MsoCF::CExclusive<Jot::CIndexerItemUrl::GlobalCacheData> Jot::CIndexerItemUrl::s_xData
0x180431849  jz      short loc_180431886
0x18043184b  mov     rcx, cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A; MsoCF::CExclusive<Jot::CIndexerItemUrl::GlobalCacheData> Jot::CIndexerItemUrl::s_xData
0x180431852  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x180431857  mov     rdx, rax; wchar_t *
0x18043185a  mov     rcx, rdi; this
0x18043185d  call    ?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x180431862  mov     rcx, rdi; this
0x180431865  call    ?IsEmpty@CWzInBuffer@Jot@@QEBA_NXZ; Jot::CWzInBuffer::IsEmpty(void)
0x18043186a  mov     bl, al
0x18043186c  xor     bl, 1
0x18043186f  lea     rcx, qword_1814ED808; _Mtx_t
0x180431876  call    cs:__imp__Mtx_unlock
0x18043187c  mov     al, bl
0x18043187e  add     rsp, 70h
0x180431882  pop     rdi
0x180431883  pop     rbx
0x180431884  pop     rbp
0x180431885  retn
0x180431886  mov     [rbp+TokenHandle], 0
0x18043188e  call    cs:__imp_GetCurrentProcess
0x180431894  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180431898  mov     edx, 8; DesiredAccess
0x18043189d  mov     rcx, rax; ProcessHandle
0x1804318a0  call    cs:__imp_OpenProcessToken
0x1804318a6  test    eax, eax
0x1804318a8  jnz     short loc_1804318CD
0x1804318aa  mov     rcx, [rbp+TokenHandle]; hObject
0x1804318ae  lea     rax, [rcx-1]
0x1804318b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1804318b6  jbe     loc_1804319E1
0x1804318bc  lea     rcx, qword_1814ED808; _Mtx_t
0x1804318c3  call    cs:__imp__Mtx_unlock
0x1804318c9  xor     al, al
0x1804318cb  jmp     short loc_18043187E
0x1804318cd  mov     [rbp+TokenInformationLength], 0
0x1804318d4  lea     rax, [rbp+TokenInformationLength]
0x1804318d8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1804318dd  xor     r9d, r9d; TokenInformationLength
0x1804318e0  xor     r8d, r8d; TokenInformation
0x1804318e3  lea     edx, [r9+1]; TokenInformationClass
0x1804318e7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1804318eb  call    cs:__imp_GetTokenInformation
0x1804318f1  call    cs:__imp_GetLastError
0x1804318f7  cmp     eax, 7Ah ; 'z'
0x1804318fa  jnz     loc_1804319BE
0x180431900  lea     r8, [rbp+var_18]
0x180431904  mov     [rbp+var_28], r8
0x180431908  mov     [rbp+var_20], 0
0x18043190f  lea     rcx, off_181515648
0x180431916  mov     [rbp+var_18], rcx
0x18043191a  mov     [rbp+var_10], 0
0x180431922  mov     [rbp+var_8], 0
0x180431929  mov     edx, [rbp+TokenInformationLength]
0x18043192c  mov     ebx, edx
0x18043192e  test    edx, edx
0x180431930  jle     short loc_180431953
0x180431932  mov     rax, cs:off_181515648
0x180431939  mov     r9b, 1
0x18043193c  mov     r8d, edx
0x18043193f  lea     rdx, [rbp+var_18]
0x180431943  mov     rax, [rax]
0x180431946  call    cs:__guard_dispatch_icall_fptr
0x18043194c  mov     edx, [rbp+TokenInformationLength]
0x18043194f  mov     r8, [rbp+var_28]
0x180431953  mov     [rbp+var_20], ebx
0x180431956  lea     rax, [rbp+TokenInformationLength]
0x18043195a  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18043195f  mov     r9d, edx; TokenInformationLength
0x180431962  mov     r8, [r8+8]; TokenInformation
0x180431966  mov     edx, 1; TokenInformationClass
0x18043196b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18043196f  call    cs:__imp_GetTokenInformation
0x180431975  test    eax, eax
0x180431977  jz      short loc_1804319AC
0x180431979  mov     rax, [rbp+var_28]
0x18043197d  mov     rcx, [rax+8]
0x180431981  mov     [rbp+StringSid], 0
0x180431989  lea     rdx, [rbp+StringSid]; StringSid
0x18043198d  mov     rcx, [rcx]; Sid
0x180431990  call    cs:__imp_ConvertSidToStringSidW
0x180431996  test    eax, eax
0x180431998  jnz     short loc_1804319EC
0x18043199a  mov     [rbp+var_20], eax
0x18043199d  mov     rcx, [rbp+var_10]
0x1804319a1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1804319a7  jmp     loc_1804318AA
0x1804319ac  mov     [rbp+var_20], 0
0x1804319b3  mov     rcx, [rbp+var_10]
0x1804319b7  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1804319bd  nop
0x1804319be  mov     rcx, [rbp+TokenHandle]; hObject
0x1804319c2  lea     rax, [rcx-1]
0x1804319c6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1804319ca  ja      short loc_1804319D3
0x1804319cc  call    cs:__imp_CloseHandle
0x1804319d2  nop
0x1804319d3  lea     rcx, [rbp+var_38]
0x1804319d7  call    ??1?$CXPtr@PEAVCWinFileProxyBase@Jot@@V?$CExclusive@PEAVCWinFileProxyBase@Jot@@@MsoCF@@@MsoCF@@QEAA@XZ; MsoCF::CXPtr<Jot::CWinFileProxyBase *,MsoCF::CExclusive<Jot::CWinFileProxyBase *>>::~CXPtr<Jot::CWinFileProxyBase *,MsoCF::CExclusive<Jot::CWinFileProxyBase *>>(void)
0x1804319dc  jmp     loc_1804318C9
0x1804319e1  call    cs:__imp_CloseHandle
0x1804319e7  jmp     loc_1804318BC
0x1804319ec  mov     ecx, 58h ; 'X'; this
0x1804319f1  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804319f6  mov     [rbp+var_40], rax
0x1804319fa  test    rax, rax
0x1804319fd  jz      short loc_180431A0C
0x1804319ff  mov     rcx, rax
0x180431a02  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CHeapBuffer@_W@2@@MsoCF@@$0A@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>(void)
0x180431a07  mov     rbx, rax
0x180431a0a  jmp     short loc_180431A0E
0x180431a0c  xor     ebx, ebx
0x180431a0e  mov     rcx, cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A; void *
0x180431a15  cmp     rcx, rbx
0x180431a18  jz      short loc_180431A2E
0x180431a1a  test    rcx, rcx
0x180431a1d  jz      short loc_180431A24
0x180431a1f  call    ??_G?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CHeapBuffer@_W@2@@MsoCF@@$0A@@Jot@@QEAAPEAXI@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::`scalar deleting destructor'(uint)
0x180431a24  mov     cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A, rbx; MsoCF::CExclusive<Jot::CIndexerItemUrl::GlobalCacheData> Jot::CIndexerItemUrl::s_xData
0x180431a2b  mov     rcx, rbx; this
0x180431a2e  lea     rdx, asc_1810F03EC; "{"
0x180431a35  call    ?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x180431a3a  mov     rdx, [rbp+StringSid]; wchar_t *
0x180431a3e  mov     rcx, cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A; this
0x180431a45  call    ?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x180431a4a  lea     rdx, SubStr; "}"
0x180431a51  mov     rcx, cs:?s_xData@CIndexerItemUrl@Jot@@0V?$CExclusive@UGlobalCacheData@CIndexerItemUrl@Jot@@@MsoCF@@A; this
0x180431a58  call    ?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x180431a5d  mov     rcx, [rbp+StringSid]; hMem
0x180431a61  call    cs:__imp_LocalFree
0x180431a67  nop
0x180431a68  mov     [rbp+var_20], 0
0x180431a6f  mov     rcx, [rbp+var_10]
0x180431a73  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180431a79  mov     rcx, [rbp+TokenHandle]; hObject
0x180431a7d  lea     rax, [rcx-1]
0x180431a81  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180431a85  ja      loc_18043184B
0x180431a8b  call    cs:__imp_CloseHandle
0x180431a91  jmp     loc_18043184B
```
