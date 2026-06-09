# CredUXParameters::CreateRandomAccessStreamFromBytes(uint,uchar const *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x14000b3a8`
- end: `0x14000b474`
- name: `?CreateRandomAccessStreamFromBytes@CredUXParameters@@AEAAJIPEBEPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(CredUXParameters *this, UINT, const unsigned __int8 *, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140018c68`

## callees

- `0x140005370`
- `0x14000b3a8`
- `0x14000e920`
- `0x14001f010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x14000b3d4`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x14000b3d4`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x14000b406`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x14000b406`

## pseudocode

```c
__int64 __fastcall CredUXParameters::CreateRandomAccessStreamFromBytes(
        CredUXParameters *this,
        UINT a2,
        const unsigned __int8 *a3,
        struct Windows::Storage::Streams::IRandomAccessStream **a4)
{
  IStream *v6; // rdi
  unsigned int v7; // ebx
  struct Windows::Storage::Streams::IRandomAccessStream *v8; // rcx
  CredUXParameters *v9; // [rsp+30h] [rbp+8h] BYREF
  int v10; // [rsp+38h] [rbp+10h] BYREF

  v9 = this;
  if ( a2 )
  {
    v6 = SHCreateMemStream(a3, a2);
    if ( v6 )
    {
      v9 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v10 = CreateRandomAccessStreamOverStream(v6, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v9);
      v7 = v10;
      if ( v10 < 0 )
      {
        CredUXTelemetry::FailedToCreateLogoStream<long &>(&v10);
      }
      else
      {
        v8 = v9;
        if ( v9 )
        {
          (*(void (__fastcall **)(CredUXParameters *))(*(_QWORD *)v9 + 8LL))(v9);
          v8 = v9;
        }
        *a4 = v8;
        v7 = 0;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return v7;
  }
  else
  {
    *a4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x14000b3a8  mov     [rsp+arg_10], rbx
0x14000b3ad  mov     [rsp+arg_18], rsi
0x14000b3b2  mov     [rsp+arg_0], rcx
0x14000b3b7  push    rdi
0x14000b3b8  sub     rsp, 20h
0x14000b3bc  mov     rsi, r9
0x14000b3bf  test    edx, edx
0x14000b3c1  jnz     short loc_14000B3D1
0x14000b3c3  mov     qword ptr [r9], 0
0x14000b3ca  xor     eax, eax
0x14000b3cc  jmp     loc_14000B464
0x14000b3d1  mov     rcx, r8; pInit
0x14000b3d4  call    cs:__imp_SHCreateMemStream
0x14000b3da  mov     rdi, rax
0x14000b3dd  test    rax, rax
0x14000b3e0  jz      short loc_14000B45D
0x14000b3e2  lea     rcx, [rsp+28h+arg_0]
0x14000b3e7  mov     [rsp+28h+arg_0], 0
0x14000b3f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000b3f5  lea     r9, [rsp+28h+arg_0]
0x14000b3fa  xor     edx, edx
0x14000b3fc  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x14000b403  mov     rcx, rdi
0x14000b406  call    cs:__imp_CreateRandomAccessStreamOverStream
0x14000b40c  mov     [rsp+28h+arg_8], eax
0x14000b410  mov     ebx, eax
0x14000b412  test    eax, eax
0x14000b414  js      short loc_14000B438
0x14000b416  mov     rcx, [rsp+28h+arg_0]
0x14000b41b  test    rcx, rcx
0x14000b41e  jz      short loc_14000B431
0x14000b420  mov     rax, [rcx]
0x14000b423  mov     rax, [rax+8]
0x14000b427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b42c  mov     rcx, [rsp+28h+arg_0]
0x14000b431  mov     [rsi], rcx
0x14000b434  xor     ebx, ebx
0x14000b436  jmp     short loc_14000B442
0x14000b438  lea     rcx, [rsp+28h+arg_8]
0x14000b43d  call    ??$FailedToCreateLogoStream@AEAJ@CredUXTelemetry@@SAXAEAJ@Z; CredUXTelemetry::FailedToCreateLogoStream<long &>(long &)
0x14000b442  lea     rcx, [rsp+28h+arg_0]
0x14000b447  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000b44c  mov     rax, [rdi]
0x14000b44f  mov     rcx, rdi
0x14000b452  mov     rax, [rax+10h]
0x14000b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b45b  jmp     short loc_14000B462
0x14000b45d  mov     ebx, 8007000Eh
0x14000b462  mov     eax, ebx
0x14000b464  mov     rbx, [rsp+28h+arg_10]
0x14000b469  mov     rsi, [rsp+28h+arg_18]
0x14000b46e  add     rsp, 20h
0x14000b472  pop     rdi
0x14000b473  retn
```
