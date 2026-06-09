# CSimpleOpenConnectRequest::HrSend(HWND__ *,HWND__ *,IMsoHSUser *,ulong,wchar_t const *,wchar_t const *,uchar *,int,wchar_t const *,int const *,ulong *,wchar_t * *,ulong *,int *,char * *,int *)

- ea: `0x180914e20`
- end: `0x1809156da`
- name: `?HrSend@CSimpleOpenConnectRequest@@QEAAJPEAUHWND__@@0PEAUIMsoHSUser@@KPEB_W2PEAEH2PEBHPEAKPEAPEA_W5PEAHPEAPEAD7@Z`
- size: `2234`
- prototype: `__int64 __usercall@<rax>(DWORD_PTR dwContext@<rcx>, HWND hWnd@<rdx>, HWND@<r8>, struct IMsoHSUser *@<r9>, unsigned int, const wchar_t *, const wchar_t *, unsigned __int8 *, DWORD dwOptionalLength, const wchar_t *, const int *, unsigned int *, wchar_t **, unsigned int *, int *, char **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1809143d4`

## callees

- `0x18023c2e0`
- `0x18023e8d0`
- `0x180914e20`
- `0x1809156dc`
- `0x180bee7a8`
- `0x1811a2ff8`
- `0x1811a3b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1809152d1`
- `KERNEL32!GetLastError` at `0x1809152d1`
- `KERNEL32!WideCharToMultiByte` at `0x180914f77`
- `KERNEL32!WideCharToMultiByte` at `0x180914f77`
- `KERNEL32!GetTickCount` at `0x180915387`
- `KERNEL32!GetTickCount` at `0x18091547f`
- `KERNEL32!GetTickCount` at `0x180915538`
- `KERNEL32!GetTickCount` at `0x180915387`
- `KERNEL32!GetTickCount` at `0x18091547f`
- `KERNEL32!GetTickCount` at `0x180915538`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x180915218`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x180915218`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18091520a`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18091540e`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x1809154a7`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18091520a`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18091540e`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x1809154a7`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x18091525c`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x18091525c`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180915437`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x1809154de`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180915437`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x1809154de`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x1809152ad`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x1809152ad`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18091562f`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18091562f`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180915266`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180915551`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180915266`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180915551`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180915339`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180915339`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180915282`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180915282`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x18091522d`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x18091522d`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x180915240`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x180915240`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1809155b8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1809155b8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180915696`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809156a8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180915696`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809156a8`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x180915029`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x180915029`
- `MSVCP140!_Mtx_unlock` at `0x180915470`
- `MSVCP140!_Mtx_unlock` at `0x180915520`
- `MSVCP140!_Mtx_unlock` at `0x180915470`
- `MSVCP140!_Mtx_unlock` at `0x180915520`
- `USER32!IsWindow` at `0x180915423`
- `USER32!IsWindow` at `0x18091543f`
- `USER32!IsWindow` at `0x1809154ca`
- `USER32!IsWindow` at `0x1809154ed`
- `USER32!IsWindow` at `0x180915423`
- `USER32!IsWindow` at `0x18091543f`
- `USER32!IsWindow` at `0x1809154ca`
- `USER32!IsWindow` at `0x1809154ed`
- `WININET!InternetSetOptionW` at `0x1809151a7`
- `WININET!InternetSetOptionW` at `0x1809151a7`
- `WININET!HttpQueryInfoW` at `0x1809152f4`
- `WININET!HttpQueryInfoW` at `0x1809155ae`
- `WININET!HttpQueryInfoW` at `0x1809155d7`
- `WININET!HttpQueryInfoW` at `0x180915611`
- `WININET!HttpQueryInfoW` at `0x1809152f4`
- `WININET!HttpQueryInfoW` at `0x1809155ae`
- `WININET!HttpQueryInfoW` at `0x1809155d7`
- `WININET!HttpQueryInfoW` at `0x180915611`
- `WININET!HttpOpenRequestA` at `0x180915185`
- `WININET!HttpOpenRequestA` at `0x180915185`
- `WININET!HttpSendRequestW` at `0x1809152bb`
- `WININET!HttpSendRequestW` at `0x1809152bb`
- `WININET!InternetCloseHandle` at `0x180915106`
- `WININET!InternetCloseHandle` at `0x180915681`
- `WININET!InternetCloseHandle` at `0x180915106`
- `WININET!InternetCloseHandle` at `0x180915681`
- `WININET!InternetErrorDlg` at `0x180915462`
- `WININET!InternetErrorDlg` at `0x180915513`
- `WININET!InternetErrorDlg` at `0x180915462`
- `WININET!InternetErrorDlg` at `0x180915513`

## pseudocode

```c

```
