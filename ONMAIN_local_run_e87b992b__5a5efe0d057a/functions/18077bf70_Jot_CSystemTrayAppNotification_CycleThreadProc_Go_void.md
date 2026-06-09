# Jot::CSystemTrayAppNotification::CycleThreadProc_Go(void)

- ea: `0x18077bf70`
- end: `0x18077c47f`
- name: `?CycleThreadProc_Go@CSystemTrayAppNotification@Jot@@UEAAXXZ`
- size: `1295`
- prototype: `void __fastcall(Jot::CSystemTrayAppNotification *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180047110`
- `0x18005ccc0`
- `0x18005ce78`
- `0x180084a4c`
- `0x18008e660`
- `0x1800935c0`
- `0x1800989e0`
- `0x18014a0d0`
- `0x180168858`
- `0x1802e2190`
- `0x1802e2251`
- `0x1802e5170`
- `0x1802e5190`
- `0x18077bf70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18077c201`
- `KERNEL32!CloseHandle` at `0x18077c20c`
- `KERNEL32!CloseHandle` at `0x18077c201`
- `KERNEL32!CloseHandle` at `0x18077c20c`
- `KERNEL32!CreateProcessW` at `0x18077c0d9`
- `KERNEL32!CreateProcessW` at `0x18077c0d9`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18077bfcb`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18077bfcb`
- `SHELL32!SHGetFolderPathW` at `0x18077c12c`
- `SHELL32!SHGetFolderPathW` at `0x18077c12c`
- `Mso98Win32Client!__imp_?MsoFGimmeFeatureEx@@YAHHK@Z` at `0x18077bfac`
- `Mso98Win32Client!__imp_?MsoFGimmeFeatureEx@@YAHHK@Z` at `0x18077bfac`
- `Mso30Win32Client!__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z` at `0x18077c03c`
- `Mso30Win32Client!__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z` at `0x18077c03c`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x18077c15d`
- `Mso20Win32Client!__imp_TWCCoCreateInstance` at `0x18077c15d`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18077c3d5`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18077c3d5`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x18077c22b`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x18077c22b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c1c8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c1e8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c388`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c3ad`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c1c8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c1e8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c388`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18077c3ad`

## pseudocode

```c
void __fastcall Jot::CSystemTrayAppNotification::CycleThreadProc_Go(Jot::CSystemTrayAppNotification *this)
{
  void (__fastcall *v2)(Jot::CSystemTrayAppNotification *, _QWORD *); // rbx
  WCHAR *v3; // rax
  void *v4; // rdx
  WCHAR *v5; // rax
  void *v6; // rdx
  int Instance; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  HINSTANCE v10; // rax
  __int64 v11; // rbx
  void (__fastcall *v12)(__int64, __int64); // rdi
  __int64 v13; // rax
  HINSTANCE v14; // rax
  bool v15; // al
  const wchar_t *v16; // rax
  __int64 v17; // rbx
  void (__fastcall *v18)(__int64, __int64, __int64); // rdi
  __int64 v19; // rax
  void *v20; // rdx
  void *v21; // rdx
  const wchar_t *v22; // rdx
  _QWORD v23[3]; // [rsp+58h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v26[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v27[40]; // [rsp+118h] [rbp+10h] BYREF
  Mso::Memory *v28; // [rsp+140h] [rbp+38h]
  char v29; // [rsp+158h] [rbp+50h] BYREF
  void *Src; // [rsp+268h] [rbp+160h] BYREF
  int v31[6]; // [rsp+270h] [rbp+168h]
  _BYTE v32[40]; // [rsp+288h] [rbp+180h] BYREF
  Mso::Memory *v33; // [rsp+2B0h] [rbp+1A8h]
  char v34; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v35[32]; // [rsp+3D8h] [rbp+2D0h] BYREF
  _BYTE v36[40]; // [rsp+3F8h] [rbp+2F0h] BYREF
  Mso::Memory *v37; // [rsp+420h] [rbp+318h]
  char v38; // [rsp+438h] [rbp+330h] BYREF
  _BYTE v39[32]; // [rsp+548h] [rbp+440h] BYREF
  _BYTE v40[40]; // [rsp+568h] [rbp+460h] BYREF
  Mso::Memory *v41; // [rsp+590h] [rbp+488h]
  char v42; // [rsp+5A8h] [rbp+4A0h] BYREF
  WCHAR ApplicationName[264]; // [rsp+6B8h] [rbp+5B0h] BYREF

  if ( MsoFGimmeFeatureEx(851969, 0x46u) )
  {
    if ( *((_DWORD *)this + 98) != 3
      || (LODWORD(v23[0]) = 0, MsoFRegGetDw(
                                 (const struct _msoreg *)&vmsoridOneNoteRunSystemTrayApp,
                                 (unsigned int *)v23))
      && LODWORD(v23[0]) == 1 )
    {
      if ( MsoFGimmeFileEx(851972, 0x409u, 0, ApplicationName, 260, 0x19u) )
      {
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        *(_QWORD *)&StartupInfo.cb = 104;
        memset_0(&StartupInfo.lpReserved, 0, 0x60u);
        Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v26);
        if ( *((_DWORD *)this + 98) != 1 )
        {
          switch ( *((_DWORD *)this + 98) )
          {
            case 2:
              v22 = L"/tsr_exit";
              break;
            case 3:
              v22 = L"/tsr";
              break;
            case 4:
              v22 = L"/screencaptureToIP";
              break;
            case 5:
              v22 = L"/screencapture_error";
              break;
            case 6:
              v22 = L"/tsr /qnote_closed";
              break;
            default:
              v22 = &WindowName;
              break;
          }
          Jot::CWzInBuffer::CopyWz((Jot::CWzInBuffer *)v26, v22);
        }
        v3 = (WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v26);
        if ( CreateProcessW(ApplicationName, v3, 0, 0, 0, 0x4000000u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          CloseHandle(ProcessInformation.hThread);
          CloseHandle(ProcessInformation.hProcess);
        }
        if ( *((_DWORD *)this + 98) == 3 )
        {
          Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v35);
          Jot::CWzInBuffer::EnsureCapacity((Jot::CWzInBuffer *)v35, 260);
          v5 = (WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v35);
          if ( SHGetFolderPathW(0, 7, 0, 0, v5) >= 0 )
          {
            v23[0] = 0;
            Instance = TWCCoCreateInstance(&CLSID_ShellLink, 0, 1, &IID_IShellLinkW, v23);
            v8 = v23[0];
            if ( Instance >= 0 )
            {
              v9 = 0;
              v23[1] = 0;
              if ( v23[0] )
              {
                (**(void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v23[0])(
                  v23[0],
                  &GUID_0000010b_0000_0000_c000_000000000046,
                  &v23[1]);
                v9 = v23[1];
                v8 = v23[0];
              }
              if ( v9 && v8 )
              {
                (*(void (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v8 + 160LL))(v8, ApplicationName);
                (*(void (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)v23[0] + 88LL))(v23[0], L"/tsr");
                Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v39);
                v10 = (HINSTANCE)Jot::TheResourceDll(0);
                Jot::CWzInBuffer::SetFromResource((Jot::CWzInBuffer *)v39, v10, 0xAE6127AD);
                v11 = v23[0];
                v12 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23[0] + 56LL);
                v13 = Jot::CWzInBuffer::operator wchar_t *(v39);
                v12(v11, v13);
                Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(&Src);
                v14 = (HINSTANCE)Jot::TheResourceDll(0);
                Jot::CWzInBuffer::SetFromResource((Jot::CWzInBuffer *)&Src, v14, 0xAE6127AD);
                if ( byte_18152D5C8 < 0 )
                  v15 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18152D5C8);
                else
                  v15 = byte_18152D5C8 != 0;
                if ( v15 )
                  std::wstring::append(Src, L".lnk");
                else
                  MsoCF::Strings::AppendArrayOfCharactersToWz((MsoCF::Memory *)L".lnk", 4, v31[0]);
                v16 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(&Src);
                Jot::CWzInBuffer::AppendFileToDirectory((Jot::CWzInBuffer *)v35, v16);
                v17 = v23[1];
                v18 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v23[1] + 48LL);
                v19 = Jot::CWzInBuffer::operator wchar_t *(v35);
                v18(v17, v19, 1);
                if ( v33 != (Mso::Memory *)&v34 )
                  Mso::Memory::Free(v33, v20);
                std::wstring::~wstring(v32);
                if ( v41 != (Mso::Memory *)&v42 )
                  Mso::Memory::Free(v41, v21);
                std::wstring::~wstring(v40);
                v9 = v23[1];
                v8 = v23[0];
              }
              if ( v9 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                v8 = v23[0];
              }
            }
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          if ( v37 != (Mso::Memory *)&v38 )
            Mso::Memory::Free(v37, v6);
          std::wstring::~wstring(v36);
        }
        if ( v28 != (Mso::Memory *)&v29 )
          Mso::Memory::Free(v28, v4);
        std::wstring::~wstring(v27);
      }
    }
  }
  v2 = *(void (__fastcall **)(Jot::CSystemTrayAppNotification *, _QWORD *))(*(_QWORD *)this + 96LL);
  *(_OWORD *)&v23[1] = 0;
  __ExceptionPtrCreate(&v23[1]);
  v2(this, &v23[1]);
}

```

## disassembly

```asm
0x18077bf70  mov     rax, rsp
0x18077bf73  mov     [rax+10h], rbx
0x18077bf77  mov     [rax+18h], rsi
0x18077bf7b  mov     [rax+20h], rdi
0x18077bf7f  push    rbp
0x18077bf80  lea     rbp, [rax-7D8h]
0x18077bf87  sub     rsp, 8D0h
0x18077bf8e  mov     rax, cs:__security_cookie
0x18077bf95  xor     rax, rsp
0x18077bf98  mov     [rbp+7D0h+var_10], rax
0x18077bf9f  mov     rsi, rcx
0x18077bfa2  mov     edx, 46h ; 'F'
0x18077bfa7  mov     ecx, 0D0001h
0x18077bfac  call    cs:__imp_?MsoFGimmeFeatureEx@@YAHHK@Z; MsoFGimmeFeatureEx(int,ulong)
0x18077bfb2  test    eax, eax
0x18077bfb4  jnz     short loc_18077C00A
0x18077bfb6  mov     rax, [rsi]
0x18077bfb9  xorps   xmm0, xmm0
0x18077bfbc  mov     rbx, [rax+60h]
0x18077bfc0  movdqu  xmmword ptr [rsp+8D0h+var_880+8], xmm0
0x18077bfc6  lea     rcx, [rsp+8D0h+var_880+8]
0x18077bfcb  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18077bfd1  lea     rdx, [rsp+8D0h+var_880+8]
0x18077bfd6  mov     rcx, rsi
0x18077bfd9  mov     rax, rbx
0x18077bfdc  call    cs:__guard_dispatch_icall_fptr
0x18077bfe2  mov     rcx, [rbp+7D0h+var_10]
0x18077bfe9  xor     rcx, rsp; StackCookie
0x18077bfec  call    __security_check_cookie
0x18077bff1  lea     r11, [rsp+8D0h+var_s0]
0x18077bff9  mov     rbx, [r11+18h]
0x18077bffd  mov     rsi, [r11+20h]
0x18077c001  mov     rdi, [r11+28h]
0x18077c005  mov     rsp, r11
0x18077c008  pop     rbp
0x18077c009  retn
0x18077c00a  cmp     dword ptr [rsi+188h], 3
0x18077c011  jz      loc_18077C217
0x18077c017  mov     [rsp+8D0h+dwCreationFlags], 19h
0x18077c01f  mov     ebx, 104h
0x18077c024  mov     [rsp+8D0h+bInheritHandles], ebx
0x18077c028  lea     r9, [rbp+7D0h+ApplicationName]
0x18077c02f  xor     r8d, r8d
0x18077c032  mov     edx, 409h
0x18077c037  mov     ecx, 0D0004h
0x18077c03c  call    cs:__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z; MsoFGimmeFileEx(int,ulong,wchar_t const *,wchar_t *,int,ulong)
0x18077c042  test    eax, eax
0x18077c044  jz      loc_18077BFB6
0x18077c04a  mov     [rsp+8D0h+ProcessInformation.hProcess], 0
0x18077c053  xorps   xmm0, xmm0
0x18077c056  movups  xmmword ptr [rsp+8D0h+ProcessInformation.hThread], xmm0
0x18077c05b  mov     qword ptr [rbp+7D0h+StartupInfo.cb], 68h ; 'h'
0x18077c063  xor     edx, edx; Val
0x18077c065  lea     r8d, [rdx+60h]; Size
0x18077c069  lea     rcx, [rbp+7D0h+StartupInfo.lpReserved]; void *
0x18077c06d  call    memset_0
0x18077c072  lea     rcx, [rbp+7D0h+var_7E0]
0x18077c076  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x18077c07b  nop
0x18077c07c  mov     ecx, [rsi+188h]
0x18077c082  sub     ecx, 1
0x18077c085  jnz     loc_18077C3F8
0x18077c08b  lea     rcx, [rbp+7D0h+var_7E0]
0x18077c08f  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x18077c094  mov     rdx, rax; lpCommandLine
0x18077c097  lea     rax, [rsp+8D0h+ProcessInformation]
0x18077c09c  mov     [rsp+8D0h+lpProcessInformation], rax; lpProcessInformation
0x18077c0a1  lea     rax, [rbp+7D0h+StartupInfo]
0x18077c0a5  mov     [rsp+8D0h+lpStartupInfo], rax; lpStartupInfo
0x18077c0aa  mov     [rsp+8D0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18077c0b3  mov     [rsp+8D0h+lpEnvironment], 0; lpEnvironment
0x18077c0bc  mov     [rsp+8D0h+dwCreationFlags], 4000000h; dwCreationFlags
0x18077c0c4  mov     [rsp+8D0h+bInheritHandles], 0; bInheritHandles
0x18077c0cc  xor     r9d, r9d; lpThreadAttributes
0x18077c0cf  xor     r8d, r8d; lpProcessAttributes
0x18077c0d2  lea     rcx, [rbp+7D0h+ApplicationName]; lpApplicationName
0x18077c0d9  call    cs:__imp_CreateProcessW
0x18077c0df  test    eax, eax
0x18077c0e1  jnz     loc_18077C1FC
0x18077c0e7  cmp     dword ptr [rsi+188h], 3
0x18077c0ee  jnz     loc_18077C1DB
0x18077c0f4  lea     rcx, [rbp+7D0h+var_500]
0x18077c0fb  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x18077c100  nop
0x18077c101  mov     edx, ebx; int
0x18077c103  lea     rcx, [rbp+7D0h+var_500]; this
0x18077c10a  call    ?EnsureCapacity@CWzInBuffer@Jot@@QEAAXH@Z; Jot::CWzInBuffer::EnsureCapacity(int)
0x18077c10f  lea     rcx, [rbp+7D0h+var_500]
0x18077c116  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x18077c11b  mov     qword ptr [rsp+8D0h+bInheritHandles], rax; pszPath
0x18077c120  xor     r9d, r9d; dwFlags
0x18077c123  xor     r8d, r8d; hToken
0x18077c126  lea     edx, [r9+7]; csidl
0x18077c12a  xor     ecx, ecx; hwnd
0x18077c12c  call    cs:__imp_SHGetFolderPathW
0x18077c132  test    eax, eax
0x18077c134  js      short loc_18077C1B5
0x18077c136  mov     qword ptr [rsp+8D0h+var_880], 0
0x18077c13f  lea     rax, [rsp+8D0h+var_880]
0x18077c144  mov     qword ptr [rsp+8D0h+bInheritHandles], rax
0x18077c149  lea     r9, IID_IShellLinkW
0x18077c150  xor     edx, edx
0x18077c152  lea     r8d, [rdx+1]
0x18077c156  lea     rcx, CLSID_ShellLink
0x18077c15d  call    cs:__imp_TWCCoCreateInstance
0x18077c163  mov     rcx, qword ptr [rsp+8D0h+var_880]
0x18077c168  test    eax, eax
0x18077c16a  js      short loc_18077C1A2
0x18077c16c  xor     eax, eax
0x18077c16e  mov     qword ptr [rsp+8D0h+var_880+8], rax
0x18077c173  test    rcx, rcx
0x18077c176  jnz     loc_18077C457
0x18077c17c  test    rax, rax
0x18077c17f  jnz     loc_18077C249
0x18077c185  test    rax, rax
0x18077c188  jz      short loc_18077C1A2
0x18077c18a  mov     rcx, [rax]
0x18077c18d  mov     rdx, [rcx+10h]
0x18077c191  mov     rcx, rax
0x18077c194  mov     rax, rdx
0x18077c197  call    cs:__guard_dispatch_icall_fptr
0x18077c19d  mov     rcx, qword ptr [rsp+8D0h+var_880]
0x18077c1a2  test    rcx, rcx
0x18077c1a5  jz      short loc_18077C1B5
0x18077c1a7  mov     rax, [rcx]
0x18077c1aa  mov     rax, [rax+10h]
0x18077c1ae  call    cs:__guard_dispatch_icall_fptr
0x18077c1b4  nop
0x18077c1b5  lea     rax, [rbp+7D0h+var_4A0]
0x18077c1bc  mov     rcx, [rbp+7D0h+var_4B8]
0x18077c1c3  cmp     rcx, rax
0x18077c1c6  jz      short loc_18077C1CE
0x18077c1c8  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18077c1ce  lea     rcx, [rbp+7D0h+var_4E0]; void *
0x18077c1d5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18077c1da  nop
0x18077c1db  lea     rax, [rbp+7D0h+var_780]
0x18077c1df  mov     rcx, [rbp+7D0h+var_798]
0x18077c1e3  cmp     rcx, rax
0x18077c1e6  jz      short loc_18077C1EE
0x18077c1e8  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18077c1ee  lea     rcx, [rbp+7D0h+var_7C0]; void *
0x18077c1f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18077c1f7  jmp     loc_18077BFB6
0x18077c1fc  mov     rcx, [rsp+8D0h+ProcessInformation.hThread]; hObject
0x18077c201  call    cs:__imp_CloseHandle
0x18077c207  mov     rcx, [rsp+8D0h+ProcessInformation.hProcess]; hObject
0x18077c20c  call    cs:__imp_CloseHandle
0x18077c212  jmp     loc_18077C0E7
0x18077c217  mov     dword ptr [rsp+8D0h+var_880], 0
0x18077c21f  lea     rdx, [rsp+8D0h+var_880]
0x18077c224  lea     rcx, ?vmsoridOneNoteRunSystemTrayApp@@3U_msoreg@@B; _msoreg const vmsoridOneNoteRunSystemTrayApp
0x18077c22b  call    cs:__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z; MsoFRegGetDw(_msoreg const *,ulong *)
0x18077c231  test    eax, eax
0x18077c233  jz      loc_18077BFB6
0x18077c239  cmp     dword ptr [rsp+8D0h+var_880], 1
0x18077c23e  jnz     loc_18077BFB6
0x18077c244  jmp     loc_18077C017
0x18077c249  test    rcx, rcx
0x18077c24c  jz      loc_18077C185
0x18077c252  mov     rax, [rcx]
0x18077c255  lea     rdx, [rbp+7D0h+ApplicationName]
0x18077c25c  mov     rax, [rax+0A0h]
0x18077c263  call    cs:__guard_dispatch_icall_fptr
0x18077c269  mov     rcx, qword ptr [rsp+8D0h+var_880]
0x18077c26e  mov     rax, [rcx]
0x18077c271  lea     rdx, aTsr; "/tsr"
0x18077c278  mov     rax, [rax+58h]
0x18077c27c  call    cs:__guard_dispatch_icall_fptr
0x18077c282  lea     rcx, [rbp+7D0h+var_390]
0x18077c289  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x18077c28e  nop
0x18077c28f  xor     ecx, ecx
0x18077c291  call    ?TheResourceDll@Jot@@YAPEAUHINSTANCE__@@W4ResourceModule@1@@Z; Jot::TheResourceDll(Jot::ResourceModule)
0x18077c296  mov     r8d, 0AE6127ADh; unsigned int
0x18077c29c  mov     rdx, rax; HINSTANCE
0x18077c29f  lea     rcx, [rbp+7D0h+var_390]; this
0x18077c2a6  call    ?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x18077c2ab  mov     rbx, qword ptr [rsp+8D0h+var_880]
0x18077c2b0  mov     rax, [rbx]
0x18077c2b3  mov     rdi, [rax+38h]
0x18077c2b7  lea     rcx, [rbp+7D0h+var_390]
0x18077c2be  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x18077c2c3  mov     rdx, rax
0x18077c2c6  mov     rcx, rbx
0x18077c2c9  mov     rax, rdi
0x18077c2cc  call    cs:__guard_dispatch_icall_fptr
0x18077c2d2  lea     rcx, [rbp+7D0h+Src]
0x18077c2d9  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x18077c2de  nop
0x18077c2df  xor     ecx, ecx
0x18077c2e1  call    ?TheResourceDll@Jot@@YAPEAUHINSTANCE__@@W4ResourceModule@1@@Z; Jot::TheResourceDll(Jot::ResourceModule)
0x18077c2e6  mov     r8d, 0AE6127ADh; unsigned int
0x18077c2ec  mov     rdx, rax; HINSTANCE
0x18077c2ef  lea     rcx, [rbp+7D0h+Src]; this
0x18077c2f6  call    ?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x18077c2fb  mov     al, cs:byte_18152D5C8
0x18077c301  test    al, al
0x18077c303  js      loc_18077C3CE
0x18077c309  setnz   al
0x18077c30c  test    al, al
0x18077c30e  jnz     loc_18077C3E0
0x18077c314  mov     r8, qword ptr [rbp+7D0h+var_668]; int
0x18077c31b  mov     edx, 4; int
0x18077c320  lea     rcx, aLnk; ".lnk"
0x18077c327  call    ?AppendArrayOfCharactersToWz@Strings@MsoCF@@YAXPEB_WHAEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@2@PEAH@Z; MsoCF::Strings::AppendArrayOfCharactersToWz(wchar_t const *,int,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CBuffer<wchar_t>> &,int *)
0x18077c32c  lea     rcx, [rbp+7D0h+Src]
0x18077c333  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x18077c338  mov     rdx, rax; wchar_t *
0x18077c33b  lea     rcx, [rbp+7D0h+var_500]; this
0x18077c342  call    ?AppendFileToDirectory@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendFileToDirectory(wchar_t const *)
0x18077c347  mov     rbx, qword ptr [rsp+8D0h+var_880+8]
0x18077c34c  mov     rax, [rbx]
0x18077c34f  mov     rdi, [rax+30h]
0x18077c353  lea     rcx, [rbp+7D0h+var_500]
0x18077c35a  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x18077c35f  mov     r8d, 1
0x18077c365  mov     rdx, rax
0x18077c368  mov     rcx, rbx
0x18077c36b  mov     rax, rdi
0x18077c36e  call    cs:__guard_dispatch_icall_fptr
0x18077c374  nop
0x18077c375  lea     rax, [rbp+7D0h+var_610]
0x18077c37c  mov     rcx, [rbp+7D0h+var_628]
0x18077c383  cmp     rcx, rax
0x18077c386  jz      short loc_18077C38E
0x18077c388  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18077c38e  lea     rcx, [rbp+7D0h+var_650]; void *
0x18077c395  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18077c39a  lea     rax, [rbp+7D0h+var_330]
0x18077c3a1  mov     rcx, [rbp+7D0h+var_348]
0x18077c3a8  cmp     rcx, rax
0x18077c3ab  jz      short loc_18077C3B3
0x18077c3ad  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18077c3b3  lea     rcx, [rbp+7D0h+var_370]; void *
0x18077c3ba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18077c3bf  mov     rcx, qword ptr [rsp+8D0h+var_880]
0x18077c3c4  mov     rax, qword ptr [rsp+8D0h+var_880+8]
0x18077c3c9  jmp     loc_18077C185
0x18077c3ce  lea     rcx, byte_18152D5C8
0x18077c3d5  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x18077c3db  jmp     loc_18077C30C
0x18077c3e0  lea     rdx, aLnk; ".lnk"
0x18077c3e7  mov     rcx, [rbp+7D0h+Src]; Src
0x18077c3ee  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18077c3f3  jmp     loc_18077C32C
0x18077c3f8  sub     ecx, 1
0x18077c3fb  jz      short loc_18077C442
0x18077c3fd  sub     ecx, 1
0x18077c400  jz      short loc_18077C439
0x18077c402  sub     ecx, 1
0x18077c405  jz      short loc_18077C430
0x18077c407  sub     ecx, 1
0x18077c40a  jz      short loc_18077C427
0x18077c40c  cmp     ecx, 1
0x18077c40f  lea     rcx, [rbp+7D0h+var_7E0]
0x18077c413  jz      short loc_18077C41E
0x18077c415  lea     rdx, WindowName
0x18077c41c  jmp     short loc_18077C44D
0x18077c41e  lea     rdx, aTsrQnoteClosed; "/tsr /qnote_closed"
0x18077c425  jmp     short loc_18077C44D
0x18077c427  lea     rdx, aScreencaptureE; "/screencapture_error"
0x18077c42e  jmp     short loc_18077C449
0x18077c430  lea     rdx, aScreencapturet_0; "/screencaptureToIP"
0x18077c437  jmp     short loc_18077C449
0x18077c439  lea     rdx, aTsr; "/tsr"
0x18077c440  jmp     short loc_18077C449
0x18077c442  lea     rdx, aTsrExit; "/tsr_exit"
0x18077c449  lea     rcx, [rbp+7D0h+var_7E0]; this
0x18077c44d  call    ?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x18077c452  jmp     loc_18077C08B
0x18077c457  mov     rax, [rcx]
0x18077c45a  lea     r8, [rsp+8D0h+var_880+8]
0x18077c45f  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18077c466  mov     rax, [rax]
0x18077c469  call    cs:__guard_dispatch_icall_fptr
0x18077c46f  mov     rcx, qword ptr [rsp+8D0h+var_880]
0x18077c474  mov     rax, qword ptr [rsp+8D0h+var_880+8]
0x18077c479  jmp     loc_18077C17C
```
