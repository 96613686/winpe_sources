# Windows::Internal::Security::Authentication::TokenBroker::GetWAB2WAMBridgeHost(ushort *,unsigned __int64)

- ea: `0x18001f1f4`
- end: `0x18001f2c1`
- name: `?GetWAB2WAMBridgeHost@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAG_K@Z`
- size: `205`
- prototype: `HRESULT __fastcall(wchar_t *pwszHostBuffer, const unsigned __int64 HostBufferSize)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9a0`

## callees

- `0x18001f1f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f247`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f247`

## string_xrefs

- `0x18001f239`: `Software\Microsoft\Windows NT\CurrentVersion\TokenBroker\WAB2WAMBridge`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetWAB2WAMBridgeHost(
        wchar_t *pwszHostBuffer,
        const unsigned __int64 HostBufferSize)
{
  wchar_t *v2; // rbx
  LSTATUS ValueW; // eax
  unsigned int v4; // ecx
  const wchar_t *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  unsigned int size; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+5Ch] [rbp+14h]

  v11 = HIDWORD(HostBufferSize);
  size = 136;
  v2 = s_WABBridgeWebAccountProviderHost;
  s_WABBridgeWebAccountProviderHost[0] = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\TokenBroker\\WAB2WAMBridge",
             L"DefaultBridgeProviderIdHost",
             0x10002u,
             0,
             s_WABBridgeWebAccountProviderHost,
             &size);
  v4 = 1;
  if ( !s_WABBridgeWebAccountProviderHost[0] || ValueW )
  {
    s_WABBridgeWebAccountProviderHost[0] = 0;
    v5 = L"WAB-23B4D62B-952A-47E7-969C-B95DBF145D3D.local";
    v6 = 2147483646;
    v7 = 68;
    do
    {
      if ( !v6 )
        break;
      if ( !*v5 )
        break;
      *v2++ = *v5++;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v2 - 1;
    if ( v7 )
      v8 = v2;
    *v8 = 0;
    return v7 == 0 ? 0x8007007A : 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001f1f4  mov     r11, rsp
0x18001f1f7  mov     [r11+8], rbx
0x18001f1fb  mov     [r11+10h], rdx
0x18001f1ff  push    rdi
0x18001f200  sub     rsp, 40h
0x18001f204  lea     rax, [r11+10h]
0x18001f208  mov     [rsp+48h+size], 88h
0x18001f210  mov     [r11-18h], rax
0x18001f214  lea     rbx, s_WABBridgeWebAccountProviderHost
0x18001f21b  xor     edi, edi
0x18001f21d  mov     [r11-20h], rbx
0x18001f221  mov     r9d, 10002h; dwFlags
0x18001f227  mov     [r11-28h], rdi
0x18001f22b  lea     r8, aDefaultbridgep; "DefaultBridgeProviderIdHost"
0x18001f232  mov     cs:s_WABBridgeWebAccountProviderHost, di
0x18001f239  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f240  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f247  call    cs:__imp_RegGetValueW
0x18001f24d  cmp     cs:s_WABBridgeWebAccountProviderHost, di
0x18001f254  lea     ecx, [rdi+1]
0x18001f257  jz      short loc_18001F25D
0x18001f259  test    eax, eax
0x18001f25b  jz      short loc_18001F2B4
0x18001f25d  mov     cs:s_WABBridgeWebAccountProviderHost, di
0x18001f264  lea     r8, aWab23b4d62b952; "WAB-23B4D62B-952A-47E7-969C-B95DBF145D3"...
0x18001f26b  mov     eax, 7FFFFFFEh
0x18001f270  mov     edx, 44h ; 'D'
0x18001f275  test    rax, rax
0x18001f278  jz      short loc_18001F298
0x18001f27a  movzx   r9d, word ptr [r8]
0x18001f27e  test    r9w, r9w
0x18001f282  jz      short loc_18001F298
0x18001f284  mov     [rbx], r9w
0x18001f288  add     r8, 2
0x18001f28c  add     rbx, 2
0x18001f290  sub     rax, rcx
0x18001f293  sub     rdx, rcx
0x18001f296  jnz     short loc_18001F275
0x18001f298  test    rdx, rdx
0x18001f29b  lea     rcx, [rbx-2]
0x18001f29f  cmovnz  rcx, rbx
0x18001f2a3  neg     rdx
0x18001f2a6  sbb     eax, eax
0x18001f2a8  not     eax
0x18001f2aa  and     eax, 8007007Ah
0x18001f2af  mov     [rcx], di
0x18001f2b2  mov     ecx, eax
0x18001f2b4  mov     rbx, [rsp+48h+arg_0]
0x18001f2b9  mov     eax, ecx
0x18001f2bb  add     rsp, 40h
0x18001f2bf  pop     rdi
0x18001f2c0  retn
```
