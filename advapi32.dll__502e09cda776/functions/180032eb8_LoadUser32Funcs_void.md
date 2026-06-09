# LoadUser32Funcs(void)

- ea: `0x180032eb8`
- end: `0x18003305b`
- name: `?LoadUser32Funcs@@YAHXZ`
- size: `419`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180032b10`
- `0x18003a788`

## callees

- `0x180032eb8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180032f45`
- `KERNEL32!GetProcAddress` at `0x180032f62`
- `KERNEL32!GetProcAddress` at `0x180032f7f`
- `KERNEL32!GetProcAddress` at `0x180032f9c`
- `KERNEL32!GetProcAddress` at `0x180032fb9`
- `KERNEL32!GetProcAddress` at `0x180032fd6`
- `KERNEL32!GetProcAddress` at `0x180032ff3`
- `KERNEL32!GetProcAddress` at `0x180032f45`
- `KERNEL32!GetProcAddress` at `0x180032f62`
- `KERNEL32!GetProcAddress` at `0x180032f7f`
- `KERNEL32!GetProcAddress` at `0x180032f9c`
- `KERNEL32!GetProcAddress` at `0x180032fb9`
- `KERNEL32!GetProcAddress` at `0x180032fd6`
- `KERNEL32!GetProcAddress` at `0x180032ff3`
- `KERNEL32!FreeLibrary` at `0x180033012`
- `KERNEL32!FreeLibrary` at `0x180033012`
- `KERNEL32!LoadLibraryExW` at `0x180032edc`
- `KERNEL32!LoadLibraryExW` at `0x180032edc`

## string_xrefs

- `0x180032ecf`: `user32.dll`

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
0x180032eb8  mov     [rsp+arg_0], rbx
0x180032ebd  push    rdi
0x180032ebe  sub     rsp, 20h
0x180032ec2  xor     edi, edi
0x180032ec4  cmp     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rdi; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x180032ecb  jnz     short loc_180032EFE
0x180032ecd  xor     edx, edx; hFile
0x180032ecf  lea     rcx, LibFileName; "user32.dll"
0x180032ed6  mov     r8d, 800h; dwFlags
0x180032edc  call    cs:__imp_LoadLibraryExW
0x180032ee3  nop     dword ptr [rax+rax+00h]
0x180032ee8  mov     rbx, rax
0x180032eeb  test    rax, rax
0x180032eee  jnz     short loc_180032F3B
0x180032ef0  xor     eax, eax
0x180032ef2  mov     rbx, [rsp+28h+arg_0]
0x180032ef7  add     rsp, 20h
0x180032efb  pop     rdi
0x180032efc  retn
0x180032efe  cmp     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rdi; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x180032f05  jz      short loc_180032ECD
0x180032f07  cmp     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rdi; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x180032f0e  jz      short loc_180032ECD
0x180032f10  cmp     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rdi; int (*pfnTranslateMessage)(tagMSG const *)
0x180032f17  jz      short loc_180032ECD
0x180032f19  cmp     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rdi; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x180032f20  jz      short loc_180032ECD
0x180032f22  cmp     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rdi; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x180032f29  jz      short loc_180032ECD
0x180032f2b  cmp     cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA, rdi; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x180032f32  jz      short loc_180032ECD
0x180032f34  mov     eax, 1
0x180032f39  jmp     short loc_180032EF2
0x180032f3b  lea     rdx, aMsgwaitformult; "MsgWaitForMultipleObjects"
0x180032f42  mov     rcx, rbx; hModule
0x180032f45  call    cs:__imp_GetProcAddress
0x180032f4c  nop     dword ptr [rax+rax+00h]
0x180032f51  lea     rdx, aPeekmessagew; "PeekMessageW"
0x180032f58  mov     rcx, rbx; hModule
0x180032f5b  mov     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rax; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x180032f62  call    cs:__imp_GetProcAddress
0x180032f69  nop     dword ptr [rax+rax+00h]
0x180032f6e  lea     rdx, aTranslatemessa; "TranslateMessage"
0x180032f75  mov     rcx, rbx; hModule
0x180032f78  mov     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rax; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x180032f7f  call    cs:__imp_GetProcAddress
0x180032f86  nop     dword ptr [rax+rax+00h]
0x180032f8b  lea     rdx, aDispatchmessag; "DispatchMessageW"
0x180032f92  mov     rcx, rbx; hModule
0x180032f95  mov     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rax; int (*pfnTranslateMessage)(tagMSG const *)
0x180032f9c  call    cs:__imp_GetProcAddress
0x180032fa3  nop     dword ptr [rax+rax+00h]
0x180032fa8  lea     rdx, aGetprocesswind_0; "GetProcessWindowStation"
0x180032faf  mov     rcx, rbx; hModule
0x180032fb2  mov     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rax; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x180032fb9  call    cs:__imp_GetProcAddress
0x180032fc0  nop     dword ptr [rax+rax+00h]
0x180032fc5  lea     rdx, aClosewindowsta; "CloseWindowStation"
0x180032fcc  mov     rcx, rbx; hModule
0x180032fcf  mov     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rax; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x180032fd6  call    cs:__imp_GetProcAddress
0x180032fdd  nop     dword ptr [rax+rax+00h]
0x180032fe2  lea     rdx, aGetuserobjecti_0; "GetUserObjectInformationW"
0x180032fe9  mov     rcx, rbx; hModule
0x180032fec  mov     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rax; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x180032ff3  call    cs:__imp_GetProcAddress
0x180032ffa  nop     dword ptr [rax+rax+00h]
0x180032fff  cmp     cs:?pfnMsgWaitForMultipleObjects@@3P6AKKPEBQEAXHKK@ZEA, rdi; ulong (*pfnMsgWaitForMultipleObjects)(ulong,void * const *,int,ulong,ulong)
0x180033006  mov     cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA, rax; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x18003300d  jnz     short loc_180033023
0x18003300f  mov     rcx, rbx; hLibModule
0x180033012  call    cs:__imp_FreeLibrary
0x180033019  nop     dword ptr [rax+rax+00h]
0x18003301e  jmp     loc_180032EF0
0x180033023  cmp     cs:?pfnPeekMessageW@@3P6AHPEAUtagMSG@@PEAUHWND__@@III@ZEA, rdi; int (*pfnPeekMessageW)(tagMSG *,HWND__ *,uint,uint,uint)
0x18003302a  jz      short loc_18003300F
0x18003302c  cmp     cs:?pfnTranslateMessage@@3P6AHPEBUtagMSG@@@ZEA, rdi; int (*pfnTranslateMessage)(tagMSG const *)
0x180033033  jz      short loc_18003300F
0x180033035  cmp     cs:?pfnDispatchMessageW@@3P6A_JPEBUtagMSG@@@ZEA, rdi; __int64 (*pfnDispatchMessageW)(tagMSG const *)
0x18003303c  jz      short loc_18003300F
0x18003303e  cmp     cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA, rdi; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x180033045  jz      short loc_18003300F
0x180033047  cmp     cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA, rdi; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x18003304e  jz      short loc_18003300F
0x180033050  test    rax, rax
0x180033053  jnz     loc_180032F34
0x180033059  jmp     short loc_18003300F
```
