# CSimpleOpenConnectRequest::HrSend(HWND__ *,HWND__ *,IMsoHSUser *,ulong,wchar_t const *,wchar_t const *,uchar *,int,wchar_t const *,int const *,ulong *,wchar_t * *,ulong *,int *,char * *,int *)

- ea: `0x180976814`
- end: `0x1809770ce`
- name: `?HrSend@CSimpleOpenConnectRequest@@QEAAJPEAUHWND__@@0PEAUIMsoHSUser@@KPEB_W2PEAEH2PEBHPEAKPEAPEA_W5PEAHPEAPEAD7@Z`
- size: `2234`
- prototype: `__int64 __usercall@<rax>(DWORD_PTR dwContext@<rcx>, HWND hWnd@<rdx>, HWND@<r8>, struct IMsoHSUser *@<r9>, unsigned int, const wchar_t *, const wchar_t *, unsigned __int8 *, DWORD dwOptionalLength, const wchar_t *, const int *, unsigned int *, wchar_t **, unsigned int *, int *, char **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180975dbc`

## callees

- `0x180485240`
- `0x180485dd0`
- `0x180976814`
- `0x1809770d0`
- `0x180c05d48`
- `0x18112cda8`
- `0x18112d8f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180976cc5`
- `KERNEL32!GetLastError` at `0x180976cc5`
- `KERNEL32!WideCharToMultiByte` at `0x18097696b`
- `KERNEL32!WideCharToMultiByte` at `0x18097696b`
- `KERNEL32!GetTickCount` at `0x180976d7b`
- `KERNEL32!GetTickCount` at `0x180976e73`
- `KERNEL32!GetTickCount` at `0x180976f2c`
- `KERNEL32!GetTickCount` at `0x180976d7b`
- `KERNEL32!GetTickCount` at `0x180976e73`
- `KERNEL32!GetTickCount` at `0x180976f2c`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x180976c0c`
- `Mso98Win32Client!__imp_?AttachRequiredAuthChallengeHeaders@CCredHelperUtils_Win@@YAXPEAX@Z` at `0x180976c0c`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976bfe`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976e02`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976e9b`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976bfe`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976e02`
- `Mso98Win32Client!__imp_?FUseOfficeCredManagerForApp@LegacyCredHelperUtils@Mso@@YA_NXZ` at `0x180976e9b`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x180976c50`
- `Mso98Win32Client!__imp_?AttachAuthHeader_Wininet@CCredHelperUtils_Win@@YA_NAEBUIMsoUrl@@PEAXPEAUIOfficeIdentity@Authentication@Mso@@_N@Z` at `0x180976c50`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180976e2b`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180976ed2`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180976e2b`
- `Mso98Win32Client!__imp_?PromptForWinInetCreds@CredCollector@Mso@@YAKPEAUHWND__@@PEAXK@Z` at `0x180976ed2`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x180976ca1`
- `Mso30Win32Client!__imp_?HttpSendRequestWithOpticsW@WinINet@Authentication@Mso@@YA_NPEAXPEB_WK0KK@Z` at `0x180976ca1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180977023`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180977023`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180976c5a`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180976f45`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180976c5a`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180976f45`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180976d2d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180976d2d`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180976c76`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180976c76`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x180976c21`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@PEAUIMsoMemHeap@@@Z` at `0x180976c21`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x180976c34`
- `Mso20Win32Client!__imp_?HrSetFromCanonicalUrl@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@@Z` at `0x180976c34`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180976fac`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180976fac`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097708a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097709c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097708a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097709c`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x180976a1d`
- `Mso20Win32Client!__imp_MsoSzMarkRgwchCore` at `0x180976a1d`
- `MSVCP140!_Mtx_unlock` at `0x180976e64`
- `MSVCP140!_Mtx_unlock` at `0x180976f14`
- `MSVCP140!_Mtx_unlock` at `0x180976e64`
- `MSVCP140!_Mtx_unlock` at `0x180976f14`
- `USER32!IsWindow` at `0x180976e17`
- `USER32!IsWindow` at `0x180976e33`
- `USER32!IsWindow` at `0x180976ebe`
- `USER32!IsWindow` at `0x180976ee1`
- `USER32!IsWindow` at `0x180976e17`
- `USER32!IsWindow` at `0x180976e33`
- `USER32!IsWindow` at `0x180976ebe`
- `USER32!IsWindow` at `0x180976ee1`
- `WININET!InternetSetOptionW` at `0x180976b9b`
- `WININET!InternetSetOptionW` at `0x180976b9b`
- `WININET!HttpQueryInfoW` at `0x180976ce8`
- `WININET!HttpQueryInfoW` at `0x180976fa2`
- `WININET!HttpQueryInfoW` at `0x180976fcb`
- `WININET!HttpQueryInfoW` at `0x180977005`
- `WININET!HttpQueryInfoW` at `0x180976ce8`
- `WININET!HttpQueryInfoW` at `0x180976fa2`
- `WININET!HttpQueryInfoW` at `0x180976fcb`
- `WININET!HttpQueryInfoW` at `0x180977005`
- `WININET!HttpOpenRequestA` at `0x180976b79`
- `WININET!HttpOpenRequestA` at `0x180976b79`
- `WININET!HttpSendRequestW` at `0x180976caf`
- `WININET!HttpSendRequestW` at `0x180976caf`
- `WININET!InternetCloseHandle` at `0x180976afa`
- `WININET!InternetCloseHandle` at `0x180977075`
- `WININET!InternetCloseHandle` at `0x180976afa`
- `WININET!InternetCloseHandle` at `0x180977075`
- `WININET!InternetErrorDlg` at `0x180976e56`
- `WININET!InternetErrorDlg` at `0x180976f07`
- `WININET!InternetErrorDlg` at `0x180976e56`
- `WININET!InternetErrorDlg` at `0x180976f07`

## pseudocode

```c

```
