# CSimpleOpenConnectRequest::HrSend(HWND__ *,HWND__ *,IMsoHSUser *,ulong,wchar_t const *,wchar_t const *,uchar *,int,wchar_t const *,int const *,ulong *,wchar_t * *,ulong *,int *,char * *,int *)

- ea: `0x18097b724`
- end: `0x18097bfde`
- name: `?HrSend@CSimpleOpenConnectRequest@@QEAAJPEAUHWND__@@0PEAUIMsoHSUser@@KPEB_W2PEAEH2PEBHPEAKPEAPEA_W5PEAHPEAPEAD7@Z`
- size: `2234`
- prototype: `__int64 __usercall@<rax>(DWORD_PTR dwContext@<rcx>, HWND hWnd@<rdx>, HWND@<r8>, struct IMsoHSUser *@<r9>, unsigned int, const wchar_t *, const wchar_t *, unsigned __int8 *, DWORD dwOptionalLength, const wchar_t *, const int *, unsigned int *, wchar_t **, unsigned int *, int *, char **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18097accc`

## callees

- `0x18016eca0`
- `0x1804860a0`
- `0x18097b724`
- `0x18097bfe0`
- `0x180c0a808`
- `0x18112d368`
- `0x18112deb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18097bbd5`
- `KERNEL32!GetLastError` at `0x18097bbd5`
- `KERNEL32!WideCharToMultiByte` at `0x18097b87b`
- `KERNEL32!WideCharToMultiByte` at `0x18097b87b`
- `KERNEL32!GetTickCount` at `0x18097bc8b`
- `KERNEL32!GetTickCount` at `0x18097bd83`
- `KERNEL32!GetTickCount` at `0x18097be3c`
- `KERNEL32!GetTickCount` at `0x18097bc8b`
- `KERNEL32!GetTickCount` at `0x18097bd83`
- `KERNEL32!GetTickCount` at `0x18097be3c`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x18097bb1c`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x18097bb1c`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bb0e`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bd12`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bdab`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bb0e`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bd12`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x18097bdab`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x18097bb60`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x18097bb60`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x18097bd3b`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x18097bde2`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x18097bd3b`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x18097bde2`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x18097bbb1`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x18097bbb1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18097bf33`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18097bf33`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18097bb6a`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18097be55`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18097bb6a`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18097be55`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18097bc3d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18097bc3d`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18097bb86`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18097bb86`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x18097bb31`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x18097bb31`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x18097bb44`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x18097bb44`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18097bebc`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18097bebc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097bf9a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097bfac`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097bf9a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097bfac`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x18097b92d`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x18097b92d`
- `MSVCP140!_Mtx_unlock` at `0x18097bd74`
- `MSVCP140!_Mtx_unlock` at `0x18097be24`
- `MSVCP140!_Mtx_unlock` at `0x18097bd74`
- `MSVCP140!_Mtx_unlock` at `0x18097be24`
- `USER32!IsWindow` at `0x18097bd27`
- `USER32!IsWindow` at `0x18097bd43`
- `USER32!IsWindow` at `0x18097bdce`
- `USER32!IsWindow` at `0x18097bdf1`
- `USER32!IsWindow` at `0x18097bd27`
- `USER32!IsWindow` at `0x18097bd43`
- `USER32!IsWindow` at `0x18097bdce`
- `USER32!IsWindow` at `0x18097bdf1`
- `WININET!InternetSetOptionW` at `0x18097baab`
- `WININET!InternetSetOptionW` at `0x18097baab`
- `WININET!HttpQueryInfoW` at `0x18097bbf8`
- `WININET!HttpQueryInfoW` at `0x18097beb2`
- `WININET!HttpQueryInfoW` at `0x18097bedb`
- `WININET!HttpQueryInfoW` at `0x18097bf15`
- `WININET!HttpQueryInfoW` at `0x18097bbf8`
- `WININET!HttpQueryInfoW` at `0x18097beb2`
- `WININET!HttpQueryInfoW` at `0x18097bedb`
- `WININET!HttpQueryInfoW` at `0x18097bf15`
- `WININET!HttpOpenRequestA` at `0x18097ba89`
- `WININET!HttpOpenRequestA` at `0x18097ba89`
- `WININET!HttpSendRequestW` at `0x18097bbbf`
- `WININET!HttpSendRequestW` at `0x18097bbbf`
- `WININET!InternetCloseHandle` at `0x18097ba0a`
- `WININET!InternetCloseHandle` at `0x18097bf85`
- `WININET!InternetCloseHandle` at `0x18097ba0a`
- `WININET!InternetCloseHandle` at `0x18097bf85`
- `WININET!InternetErrorDlg` at `0x18097bd66`
- `WININET!InternetErrorDlg` at `0x18097be17`
- `WININET!InternetErrorDlg` at `0x18097bd66`
- `WININET!InternetErrorDlg` at `0x18097be17`

## pseudocode

```c

```
