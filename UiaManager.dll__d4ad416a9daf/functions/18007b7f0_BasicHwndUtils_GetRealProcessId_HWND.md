# BasicHwndUtils::GetRealProcessId(HWND__ *)

- ea: `0x18007b7f0`
- end: `0x18007b897`
- name: `?GetRealProcessId@BasicHwndUtils@@SAKPEAUHWND__@@@Z`
- size: `167`
- prototype: `unsigned int __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004061c`

## callees

- `0x180049c3c`
- `0x180049ca4`
- `0x18007b7f0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b853`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b840`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b840`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007b887`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18007b887`

## string_xrefs

- `0x18007b839`: `user32.dll`

## pseudocode

```c
__int64 __fastcall BasicHwndUtils::GetRealProcessId(HWND hWnd)
{
  HMODULE LibraryW; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  if ( dword_1800C5250 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 128LL) )
  {
    Init_thread_header(&dword_1800C5250);
    if ( dword_1800C5250 == -1 )
    {
      LibraryW = LoadLibraryW(L"user32.dll");
      if ( LibraryW )
        LibraryW = (HMODULE)GetProcAddress(LibraryW, (LPCSTR)0xA98);
      qword_1800C5258 = (__int64 (__fastcall *)(_QWORD))LibraryW;
      Init_thread_footer(&dword_1800C5250);
    }
  }
  if ( qword_1800C5258 )
    return qword_1800C5258(hWnd);
  GetWindowThreadProcessId(hWnd, &dwProcessId);
  return dwProcessId;
}

```

## disassembly

```asm
0x18007b7f0  push    rbx
0x18007b7f2  sub     rsp, 20h
0x18007b7f6  mov     rbx, rcx
0x18007b7f9  mov     [rsp+28h+dwProcessId], 0
0x18007b801  mov     edx, cs:_tls_index
0x18007b807  mov     rax, gs:58h
0x18007b810  mov     ecx, 80h
0x18007b815  mov     rax, [rax+rdx*8]
0x18007b819  mov     eax, [rcx+rax]
0x18007b81c  cmp     cs:dword_1800C5250, eax
0x18007b822  jle     short loc_18007B86C
0x18007b824  lea     rcx, dword_1800C5250
0x18007b82b  call    _Init_thread_header
0x18007b830  cmp     cs:dword_1800C5250, 0FFFFFFFFh
0x18007b837  jnz     short loc_18007B86C
0x18007b839  lea     rcx, aUser32Dll; "user32.dll"
0x18007b840  call    cs:__imp_LoadLibraryW
0x18007b846  test    rax, rax
0x18007b849  jz      short loc_18007B859
0x18007b84b  mov     edx, 0A98h; lpProcName
0x18007b850  mov     rcx, rax; hModule
0x18007b853  call    cs:__imp_GetProcAddress
0x18007b859  mov     cs:qword_1800C5258, rax
0x18007b860  lea     rcx, dword_1800C5250
0x18007b867  call    _Init_thread_footer
0x18007b86c  mov     rax, cs:qword_1800C5258
0x18007b873  mov     rcx, rbx; hWnd
0x18007b876  test    rax, rax
0x18007b879  jz      short loc_18007B882
0x18007b87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b880  jmp     short loc_18007B891
0x18007b882  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18007b887  call    cs:__imp_GetWindowThreadProcessId
0x18007b88d  mov     eax, [rsp+28h+dwProcessId]
0x18007b891  add     rsp, 20h
0x18007b895  pop     rbx
0x18007b896  retn
```
