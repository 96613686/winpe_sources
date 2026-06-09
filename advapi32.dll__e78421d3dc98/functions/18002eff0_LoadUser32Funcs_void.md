# LoadUser32Funcs(void)

- ea: `0x18002eff0`
- end: `0x18002f15c`
- name: `?LoadUser32Funcs@@YAHXZ`
- size: `364`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18002ec80`
- `0x1800367f0`

## callees

- `0x18002eff0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002f076`
- `KERNEL32!GetProcAddress` at `0x18002f08d`
- `KERNEL32!GetProcAddress` at `0x18002f0a4`
- `KERNEL32!GetProcAddress` at `0x18002f0bb`
- `KERNEL32!GetProcAddress` at `0x18002f0d2`
- `KERNEL32!GetProcAddress` at `0x18002f0e9`
- `KERNEL32!GetProcAddress` at `0x18002f100`
- `KERNEL32!GetProcAddress` at `0x18002f076`
- `KERNEL32!GetProcAddress` at `0x18002f08d`
- `KERNEL32!GetProcAddress` at `0x18002f0a4`
- `KERNEL32!GetProcAddress` at `0x18002f0bb`
- `KERNEL32!GetProcAddress` at `0x18002f0d2`
- `KERNEL32!GetProcAddress` at `0x18002f0e9`
- `KERNEL32!GetProcAddress` at `0x18002f100`
- `KERNEL32!FreeLibrary` at `0x18002f119`
- `KERNEL32!FreeLibrary` at `0x18002f119`
- `KERNEL32!LoadLibraryExW` at `0x18002f014`
- `KERNEL32!LoadLibraryExW` at `0x18002f014`

## string_xrefs

- `0x18002f007`: `user32.dll`

## pseudocode

```c
__int64 LoadUser32Funcs(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  int (*ProcAddress)(void *, int, void *, unsigned int, unsigned int *); // rax

  if ( pfnMsgWaitForMultipleObjects
    && pfnCloseWindowStation
    && pfnPeekMessageW
    && pfnTranslateMessage
    && pfnDispatchMessageW
    && pfnGetProcessWindowStation
    && pfnGetUserObjectInformationW )
  {
    return 1;
  }
  Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
  v1 = Library;
  if ( !Library )
    return 0;
  pfnMsgWaitForMultipleObjects = (unsigned int (*)(unsigned int, void *const *, int, unsigned int, unsigned int))GetProcAddress(Library, "MsgWaitForMultipleObjects");
  pfnPeekMessageW = (int (*)(struct tagMSG *, HWND, unsigned int, unsigned int, unsigned int))GetProcAddress(
                                                                                                v1,
                                                                                                "PeekMessageW");
  pfnTranslateMessage = (int (*)(const struct tagMSG *))GetProcAddress(v1, "TranslateMessage");
  pfnDispatchMessageW = (__int64 (*)(const struct tagMSG *))GetProcAddress(v1, "DispatchMessageW");
  pfnGetProcessWindowStation = (HWINSTA (*)(void))GetProcAddress(v1, "GetProcessWindowStation");
  pfnCloseWindowStation = (int (*)(HWINSTA))GetProcAddress(v1, "CloseWindowStation");
  ProcAddress = (int (*)(void *, int, void *, unsigned int, unsigned int *))GetProcAddress(
                                                                              v1,
                                                                              "GetUserObjectInformationW");
  pfnGetUserObjectInformationW = ProcAddress;
  if ( !pfnMsgWaitForMultipleObjects
    || !pfnPeekMessageW
    || !pfnTranslateMessage
    || !pfnDispatchMessageW
    || !pfnGetProcessWindowStation
    || !pfnCloseWindowStation
    || !ProcAddress )
  {
    FreeLibrary(v1);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18002eff0  mov     [rsp+arg_0], rbx
0x18002eff5  push    rdi
0x18002eff6  sub     rsp, 20h
0x18002effa  xor     edi, edi
0x18002effc  cmp     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rdi; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x18002f003  jnz     short loc_18002F02F
0x18002f005  xor     edx, edx; hFile
0x18002f007  lea     rcx, LibFileName; "user32.dll"
0x18002f00e  mov     r8d, 800h; dwFlags
0x18002f014  call    cs:__imp_LoadLibraryExW
0x18002f01a  mov     rbx, rax
0x18002f01d  test    rax, rax
0x18002f020  jnz     short loc_18002F06C
0x18002f022  xor     eax, eax
0x18002f024  mov     rbx, [rsp+28h+arg_0]
0x18002f029  add     rsp, 20h
0x18002f02d  pop     rdi
0x18002f02e  retn
0x18002f02f  cmp     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rdi; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x18002f036  jz      short loc_18002F005
0x18002f038  cmp     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rdi; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x18002f03f  jz      short loc_18002F005
0x18002f041  cmp     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rdi; int (*pfnTranslateMessage)(tagMSG const *)
0x18002f048  jz      short loc_18002F005
0x18002f04a  cmp     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rdi; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x18002f051  jz      short loc_18002F005
0x18002f053  cmp     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rdi; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x18002f05a  jz      short loc_18002F005
0x18002f05c  cmp     cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA, rdi; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x18002f063  jz      short loc_18002F005
0x18002f065  mov     eax, 1
0x18002f06a  jmp     short loc_18002F024
0x18002f06c  lea     rdx, aMsgwaitformult; "MsgWaitForMultipleObjects"
0x18002f073  mov     rcx, rbx; hModule
0x18002f076  call    cs:__imp_GetProcAddress
0x18002f07c  lea     rdx, aPeekmessagew; "PeekMessageW"
0x18002f083  mov     rcx, rbx; hModule
0x18002f086  mov     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rax; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x18002f08d  call    cs:__imp_GetProcAddress
0x18002f093  lea     rdx, aTranslatemessa; "TranslateMessage"
0x18002f09a  mov     rcx, rbx; hModule
0x18002f09d  mov     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rax; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x18002f0a4  call    cs:__imp_GetProcAddress
0x18002f0aa  lea     rdx, aDispatchmessag; "DispatchMessageW"
0x18002f0b1  mov     rcx, rbx; hModule
0x18002f0b4  mov     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rax; int (*pfnTranslateMessage)(tagMSG const *)
0x18002f0bb  call    cs:__imp_GetProcAddress
0x18002f0c1  lea     rdx, aGetprocesswind_0; "GetProcessWindowStation"
0x18002f0c8  mov     rcx, rbx; hModule
0x18002f0cb  mov     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rax; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x18002f0d2  call    cs:__imp_GetProcAddress
0x18002f0d8  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x18002f0df  mov     rcx, rbx; hModule
0x18002f0e2  mov     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rax; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x18002f0e9  call    cs:__imp_GetProcAddress
0x18002f0ef  lea     rdx, aGetuserobjecti_0; "GetUserObjectInformationW"
0x18002f0f6  mov     rcx, rbx; hModule
0x18002f0f9  mov     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rax; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x18002f100  call    cs:__imp_GetProcAddress
0x18002f106  cmp     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rdi; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x18002f10d  mov     cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA, rax; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x18002f114  jnz     short loc_18002F124
0x18002f116  mov     rcx, rbx; hLibModule
0x18002f119  call    cs:__imp_FreeLibrary
0x18002f11f  jmp     loc_18002F022
0x18002f124  cmp     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rdi; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x18002f12b  jz      short loc_18002F116
0x18002f12d  cmp     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rdi; int (*pfnTranslateMessage)(tagMSG const *)
0x18002f134  jz      short loc_18002F116
0x18002f136  cmp     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rdi; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x18002f13d  jz      short loc_18002F116
0x18002f13f  cmp     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rdi; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x18002f146  jz      short loc_18002F116
0x18002f148  cmp     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rdi; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x18002f14f  jz      short loc_18002F116
0x18002f151  test    rax, rax
0x18002f154  jnz     loc_18002F065
0x18002f15a  jmp     short loc_18002F116
```
