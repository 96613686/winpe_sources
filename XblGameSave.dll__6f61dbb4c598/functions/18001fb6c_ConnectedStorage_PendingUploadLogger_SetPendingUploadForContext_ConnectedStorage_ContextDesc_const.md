# ConnectedStorage::PendingUploadLogger::SetPendingUploadForContext(ConnectedStorage::ContextDesc const &)

- ea: `0x18001fb6c`
- end: `0x18001fc69`
- name: `?SetPendingUploadForContext@PendingUploadLogger@ConnectedStorage@@SAXAEBVContextDesc@2@@Z`
- size: `253`
- prototype: `void __fastcall(HSTRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180053470`
- `0x18005e740`

## callees

- `0x18000ab18`
- `0x180015f7c`
- `0x18001ef04`
- `0x18001f8dc`
- `0x18001f984`
- `0x18001f9d8`
- `0x18001fb6c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001fbd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001fbd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fbe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fbe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fbf5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fc13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fc13`

## string_xrefs

- `0x18001fc27`: `CreatePendingUploadEntryUnderXuidKey`

## pseudocode

```c
void __fastcall ConnectedStorage::PendingUploadLogger::SetPendingUploadForContext(HSTRING *a1)
{
  __int64 v2; // r9
  ConnectedStorage *v3; // rcx
  __int64 v4; // r9
  HKEY v5; // rbp
  DWORD cbData; // edi
  const BYTE *lpData; // rbx
  const WCHAR *StringRawBuffer; // rax
  int v9; // eax
  const unsigned __int16 *v10; // r8
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  ConnectedStorage::GetRootKey((ConnectedStorage *)&v13);
  if ( v13 )
  {
    LOBYTE(v2) = 1;
    ConnectedStorage::GetUserKeyFromRoot(&v12, v13, a1 + 1, v2);
    if ( v12 )
    {
      LOBYTE(v4) = 1;
      ConnectedStorage::GetXuidKeyFromUser(&hKey, v12, a1 + 2, v4);
      v5 = hKey;
      if ( hKey )
      {
        cbData = 2 * WindowsGetStringLen(a1[3]) + 2;
        lpData = (const BYTE *)WindowsGetStringRawBuffer(a1[3], 0);
        StringRawBuffer = WindowsGetStringRawBuffer(a1[4], 0);
        v9 = RegSetValueExW(v5, StringRawBuffer, 0, 1u, lpData, cbData);
        if ( v9 )
        {
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          ConnectedStorage::ReportErrorNoThrow(
            (ConnectedStorage *)(unsigned int)v9,
            (int)L"CreatePendingUploadEntryUnderXuidKey",
            v10);
        }
      }
      ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&hKey);
    }
    LOBYTE(v3) = 1;
    ConnectedStorage::ChangeServiceStart(v3);
    ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&v12);
  }
  ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&v13);
}

```

## disassembly

```asm
0x18001fb6c  mov     [rsp+arg_0], rbx
0x18001fb71  push    rbp
0x18001fb72  push    rsi
0x18001fb73  push    rdi
0x18001fb74  sub     rsp, 30h
0x18001fb78  mov     rsi, rcx
0x18001fb7b  lea     rcx, [rsp+48h+arg_18]
0x18001fb80  call    ?GetRootKey@ConnectedStorage@@YA?AVHKey@1@XZ; ConnectedStorage::GetRootKey(void)
0x18001fb85  nop
0x18001fb86  mov     rdx, [rsp+48h+arg_18]
0x18001fb8b  test    rdx, rdx
0x18001fb8e  jz      loc_18001FC52
0x18001fb94  lea     r8, [rsi+8]
0x18001fb98  mov     r9b, 1
0x18001fb9b  lea     rcx, [rsp+48h+arg_10]
0x18001fba0  call    ?GetUserKeyFromRoot@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetUserKeyFromRoot(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001fba5  nop
0x18001fba6  mov     rdx, [rsp+48h+arg_10]
0x18001fbab  test    rdx, rdx
0x18001fbae  jz      loc_18001FC3F
0x18001fbb4  lea     r8, [rsi+10h]
0x18001fbb8  mov     r9b, 1
0x18001fbbb  lea     rcx, [rsp+48h+hKey]
0x18001fbc0  call    ?GetXuidKeyFromUser@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetXuidKeyFromUser(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001fbc5  mov     rbp, [rsp+48h+hKey]
0x18001fbca  test    rbp, rbp
0x18001fbcd  jz      short loc_18001FC35
0x18001fbcf  mov     rcx, [rsi+18h]; string
0x18001fbd3  call    cs:__imp_WindowsGetStringLen
0x18001fbd9  lea     edi, ds:2[rax*2]
0x18001fbe0  xor     edx, edx; length
0x18001fbe2  mov     rcx, [rsi+18h]; string
0x18001fbe6  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fbec  mov     rbx, rax
0x18001fbef  xor     edx, edx; length
0x18001fbf1  mov     rcx, [rsi+20h]; string
0x18001fbf5  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fbfb  mov     [rsp+48h+cbData], edi; cbData
0x18001fbff  mov     [rsp+48h+lpData], rbx; lpData
0x18001fc04  mov     r9d, 1; dwType
0x18001fc0a  xor     r8d, r8d; Reserved
0x18001fc0d  mov     rdx, rax; lpValueName
0x18001fc10  mov     rcx, rbp; hKey
0x18001fc13  call    cs:__imp_RegSetValueExW
0x18001fc19  test    eax, eax
0x18001fc1b  jz      short loc_18001FC35
0x18001fc1d  jle     short loc_18001FC27
0x18001fc1f  movzx   eax, ax
0x18001fc22  or      eax, 80070000h
0x18001fc27  lea     rdx, aCreatependingu; "CreatePendingUploadEntryUnderXuidKey"
0x18001fc2e  mov     ecx, eax; this
0x18001fc30  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18001fc35  lea     rcx, [rsp+48h+hKey]; this
0x18001fc3a  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001fc3f  mov     cl, 1; this
0x18001fc41  call    ?ChangeServiceStart@ConnectedStorage@@YAX_N@Z; ConnectedStorage::ChangeServiceStart(bool)
0x18001fc46  nop
0x18001fc47  lea     rcx, [rsp+48h+arg_10]; this
0x18001fc4c  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001fc51  nop
0x18001fc52  lea     rcx, [rsp+48h+arg_18]; this
0x18001fc57  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001fc5c  mov     rbx, [rsp+48h+arg_0]
0x18001fc61  add     rsp, 30h
0x18001fc65  pop     rdi
0x18001fc66  pop     rsi
0x18001fc67  pop     rbp
0x18001fc68  retn
```
