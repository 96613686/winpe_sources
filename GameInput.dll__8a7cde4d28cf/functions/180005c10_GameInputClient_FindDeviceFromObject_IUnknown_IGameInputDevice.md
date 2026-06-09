# GameInputClient::FindDeviceFromObject(IUnknown *,IGameInputDevice * *)

- ea: `0x180005c10`
- end: `0x180005eaa`
- name: `?FindDeviceFromObject@GameInputClient@@UEAAJPEAUIUnknown@@PEAPEAUIGameInputDevice@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(GameInputClient *__hidden this, struct IUnknown *, struct IGameInputDevice **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b60`
- `0x180005c10`
- `0x180005eb0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005de6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005de6`

## pseudocode

```c
__int64 __fastcall GameInputClient::FindDeviceFromObject(
        GameInputClient *this,
        struct IUnknown *a2,
        struct IGameInputDevice **a3)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  unsigned int DeviceFromId; // edi
  struct IUnknownVtbl *lpVtbl; // rax
  HSTRING v12; // rcx
  struct IUnknownVtbl *v13; // rax
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h] BYREF
  int (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-10h] BYREF
  HSTRING v19; // [rsp+78h] [rbp+38h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  QueryInterface = a2->lpVtbl->QueryInterface;
  v17 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_31dd86fb_4c1b_408a_868f_439b3cd47125,
         &v17) >= 0 )
  {
    v7 = v17;
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
    DeviceFromId = GameInputClient::FindDeviceFromId(this, (const struct APP_LOCAL_DEVICE_ID *)(v8 + 32), a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return DeviceFromId;
  }
  lpVtbl = a2->lpVtbl;
  v19 = 0;
  string = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, HSTRING *))lpVtbl->QueryInterface)(
         a2,
         &GUID_c3542377_1ea7_4454_8deb_8aa6070db645,
         &string) < 0 )
  {
    v13 = a2->lpVtbl;
    v18 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))v13->QueryInterface)(
           a2,
           &GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd,
           &v18) >= 0 )
    {
      v14 = v18;
      v16 = 0;
      if ( (**v18)(v18, &GUID_debcfefe_f763_4670_940b_57aae2b143ff, &v16) >= 0 )
      {
        string = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, HSTRING *))v16)(
               v16,
               &GUID_e6d73982_2996_4559_b16c_3e57d46e58d6,
               &string) >= 0 )
        {
          if ( v19 )
          {
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
            v19 = 0;
          }
          (**(void (__fastcall ***)(HSTRING, GUID *, HSTRING *))string)(
            string,
            &GUID_c3542377_1ea7_4454_8deb_8aa6070db645,
            &v19);
        }
        if ( string )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v14 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
    }
    v12 = v19;
  }
  else
  {
    if ( v19 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
    v12 = string;
    v19 = string;
  }
  if ( v12 )
  {
    string = 0;
    if ( (*(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v12 + 136LL))(v12, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
      {
        DeviceFromId = GameInputClient::FindDeviceFromPlatformString(this, StringRawBuffer, a3);
        if ( string )
        {
          WindowsDeleteString(string);
          string = 0;
        }
        if ( v19 )
        {
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
        return DeviceFromId;
      }
    }
    if ( string )
      WindowsDeleteString(string);
    v12 = v19;
  }
  *a3 = 0;
  if ( v12 )
  {
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v12 + 16LL))(v12);
    v19 = 0;
  }
  return 2206859266LL;
}

```

## disassembly

```asm
0x180005c10  mov     [rsp-28h+arg_0], rbx
0x180005c15  push    rbp
0x180005c16  push    rsi
0x180005c17  push    rdi
0x180005c18  push    r14
0x180005c1a  push    r15
0x180005c1c  mov     rbp, rsp
0x180005c1f  sub     rsp, 40h
0x180005c23  mov     rax, [rdx]
0x180005c26  mov     rbx, rdx
0x180005c29  mov     rsi, r8
0x180005c2c  lea     rdx, _GUID_31dd86fb_4c1b_408a_868f_439b3cd47125
0x180005c33  mov     r14, rcx
0x180005c36  lea     r8, [rbp+var_18]
0x180005c3a  xor     r15d, r15d
0x180005c3d  mov     rcx, rbx
0x180005c40  mov     rax, [rax]
0x180005c43  mov     [rbp+var_18], r15
0x180005c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4c  test    eax, eax
0x180005c4e  js      short loc_180005C8A
0x180005c50  mov     rbx, [rbp+var_18]
0x180005c54  mov     rcx, rbx
0x180005c57  mov     rax, [rbx]
0x180005c5a  mov     rax, [rax+18h]
0x180005c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c63  mov     r8, rsi; struct IGameInputDevice **
0x180005c66  mov     rcx, r14; this
0x180005c69  lea     rdx, [rax+20h]; struct APP_LOCAL_DEVICE_ID *
0x180005c6d  call    ?FindDeviceFromId@GameInputClient@@UEAAJPEBUAPP_LOCAL_DEVICE_ID@@PEAPEAUIGameInputDevice@@@Z; GameInputClient::FindDeviceFromId(APP_LOCAL_DEVICE_ID const *,IGameInputDevice * *)
0x180005c72  mov     rcx, [rbx]
0x180005c75  mov     edi, eax
0x180005c77  mov     rax, [rcx+10h]
0x180005c7b  mov     rcx, rbx
0x180005c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c83  mov     eax, edi
0x180005c85  jmp     loc_180005E98
0x180005c8a  mov     rax, [rbx]
0x180005c8d  lea     r8, [rbp+string]
0x180005c91  lea     rdx, _GUID_c3542377_1ea7_4454_8deb_8aa6070db645
0x180005c98  mov     [rbp+arg_8], r15
0x180005c9c  mov     rcx, rbx
0x180005c9f  mov     [rbp+string], r15
0x180005ca3  mov     rax, [rax]
0x180005ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cab  test    eax, eax
0x180005cad  js      short loc_180005CD4
0x180005caf  mov     rcx, [rbp+arg_8]
0x180005cb3  test    rcx, rcx
0x180005cb6  jz      short loc_180005CC4
0x180005cb8  mov     rax, [rcx]
0x180005cbb  mov     rax, [rax+10h]
0x180005cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc4  mov     rcx, [rbp+string]
0x180005cc8  mov     rbx, r15
0x180005ccb  mov     [rbp+arg_8], rcx
0x180005ccf  jmp     loc_180005DBC
0x180005cd4  mov     rax, [rbx]
0x180005cd7  lea     r8, [rbp+var_10]
0x180005cdb  lea     rdx, _GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd
0x180005ce2  mov     [rbp+var_10], r15
0x180005ce6  mov     rcx, rbx
0x180005ce9  mov     rax, [rax]
0x180005cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf1  test    eax, eax
0x180005cf3  jns     short loc_180005CFD
0x180005cf5  mov     rbx, r15
0x180005cf8  jmp     loc_180005DB8
0x180005cfd  mov     rdi, [rbp+var_10]
0x180005d01  lea     r8, [rbp+var_20]
0x180005d05  lea     rdx, _GUID_debcfefe_f763_4670_940b_57aae2b143ff
0x180005d0c  mov     [rbp+var_20], r15
0x180005d10  mov     rcx, rdi
0x180005d13  mov     rax, [rdi]
0x180005d16  mov     rax, [rax]
0x180005d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1e  test    eax, eax
0x180005d20  js      short loc_180005D8C
0x180005d22  mov     rcx, [rbp+var_20]
0x180005d26  lea     r8, [rbp+string]
0x180005d2a  mov     [rbp+string], r15
0x180005d2e  lea     rdx, _GUID_e6d73982_2996_4559_b16c_3e57d46e58d6
0x180005d35  mov     rax, [rcx]
0x180005d38  mov     rax, [rax]
0x180005d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d40  test    eax, eax
0x180005d42  js      short loc_180005D77
0x180005d44  mov     rcx, [rbp+arg_8]
0x180005d48  test    rcx, rcx
0x180005d4b  jz      short loc_180005D5D
0x180005d4d  mov     rax, [rcx]
0x180005d50  mov     rax, [rax+10h]
0x180005d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d59  mov     [rbp+arg_8], r15
0x180005d5d  mov     rcx, [rbp+string]
0x180005d61  lea     r8, [rbp+arg_8]
0x180005d65  lea     rdx, _GUID_c3542377_1ea7_4454_8deb_8aa6070db645
0x180005d6c  mov     rax, [rcx]
0x180005d6f  mov     rax, [rax]
0x180005d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d77  mov     rcx, [rbp+string]
0x180005d7b  test    rcx, rcx
0x180005d7e  jz      short loc_180005D8C
0x180005d80  mov     rax, [rcx]
0x180005d83  mov     rax, [rax+10h]
0x180005d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8c  mov     rcx, [rbp+var_20]
0x180005d90  test    rcx, rcx
0x180005d93  jz      short loc_180005DA1
0x180005d95  mov     rax, [rcx]
0x180005d98  mov     rax, [rax+10h]
0x180005d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da1  mov     rbx, r15
0x180005da4  test    rdi, rdi
0x180005da7  jz      short loc_180005DB8
0x180005da9  mov     rax, [rdi]
0x180005dac  mov     rcx, rdi
0x180005daf  mov     rax, [rax+10h]
0x180005db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db8  mov     rcx, [rbp+arg_8]
0x180005dbc  test    rcx, rcx
0x180005dbf  jz      loc_180005E67
0x180005dc5  mov     [rbp+string], r15
0x180005dc9  lea     rdx, [rbp+string]
0x180005dcd  mov     rax, [rcx]
0x180005dd0  mov     rax, [rax+88h]
0x180005dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ddc  test    eax, eax
0x180005dde  js      short loc_180005E4E
0x180005de0  mov     rcx, [rbp+string]; string
0x180005de4  xor     edx, edx; length
0x180005de6  call    cs:__imp_WindowsGetStringRawBuffer
0x180005ded  nop     dword ptr [rax+rax+00h]
0x180005df2  test    rax, rax
0x180005df5  jz      short loc_180005E4E
0x180005df7  mov     r8, rsi; struct IGameInputDevice **
0x180005dfa  mov     rdx, rax; unsigned __int16 *
0x180005dfd  mov     rcx, r14; this
0x180005e00  call    ?FindDeviceFromPlatformString@GameInputClient@@UEAAJPEBGPEAPEAUIGameInputDevice@@@Z; GameInputClient::FindDeviceFromPlatformString(ushort const *,IGameInputDevice * *)
0x180005e05  mov     rcx, [rbp+string]; string
0x180005e09  mov     edi, eax
0x180005e0b  test    rcx, rcx
0x180005e0e  jz      short loc_180005E20
0x180005e10  call    cs:__imp_WindowsDeleteString
0x180005e17  nop     dword ptr [rax+rax+00h]
0x180005e1c  mov     [rbp+string], r15
0x180005e20  mov     rcx, [rbp+arg_8]
0x180005e24  test    rcx, rcx
0x180005e27  jz      short loc_180005E39
0x180005e29  mov     rdx, [rcx]
0x180005e2c  mov     rax, [rdx+10h]
0x180005e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e35  mov     [rbp+arg_8], r15
0x180005e39  test    rbx, rbx
0x180005e3c  jz      loc_180005C83
0x180005e42  mov     rax, [rbx]
0x180005e45  mov     rax, [rax+10h]
0x180005e49  jmp     loc_180005C7B
0x180005e4e  mov     rcx, [rbp+string]; string
0x180005e52  test    rcx, rcx
0x180005e55  jz      short loc_180005E63
0x180005e57  call    cs:__imp_WindowsDeleteString
0x180005e5e  nop     dword ptr [rax+rax+00h]
0x180005e63  mov     rcx, [rbp+arg_8]
0x180005e67  mov     [rsi], r15
0x180005e6a  test    rcx, rcx
0x180005e6d  jz      short loc_180005E7F
0x180005e6f  mov     rax, [rcx]
0x180005e72  mov     rax, [rax+10h]
0x180005e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7b  mov     [rbp+arg_8], r15
0x180005e7f  test    rbx, rbx
0x180005e82  jz      short loc_180005E93
0x180005e84  mov     rax, [rbx]
0x180005e87  mov     rcx, rbx
0x180005e8a  mov     rax, [rax+10h]
0x180005e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e93  mov     eax, 838A0002h
0x180005e98  mov     rbx, [rsp+40h+arg_0]
0x180005e9d  add     rsp, 40h
0x180005ea1  pop     r15
0x180005ea3  pop     r14
0x180005ea5  pop     rdi
0x180005ea6  pop     rsi
0x180005ea7  pop     rbp
0x180005ea8  retn
```
