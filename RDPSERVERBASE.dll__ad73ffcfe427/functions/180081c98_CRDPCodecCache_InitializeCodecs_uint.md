# CRDPCodecCache::InitializeCodecs(uint)

- ea: `0x180081c98`
- end: `0x180081f9b`
- name: `?InitializeCodecs@CRDPCodecCache@@IEAAJI@Z`
- size: `771`
- prototype: `__int64 __fastcall(CRDPCodecCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081fb0`

## callees

- `0x180076090`
- `0x180077770`
- `0x18007a664`
- `0x180081c98`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081d58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081dc0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081e2e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081e96`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081f04`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081f59`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081d58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081dc0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081e2e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081e96`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081f04`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180081f59`

## string_xrefs

- `0x180081e39`: `Failed To create legacy Compressor`
- `0x180081ea1`: `Failed To create legacy Decompressor`
- `0x180081f0f`: `Failed To create Nscodec Compressor`
- `0x180081f64`: `Failed To create Nscodec Decompressor`
- `0x180081d63`: `Failed To create CAC Compressor`
- `0x180081dcb`: `Failed To create CAC Decompressor`

## pseudocode

```c
__int64 __fastcall CRDPCodecCache::InitializeCodecs(CRDPCodecCache *this, int a2)
{
  int v3; // edx
  int v4; // edx
  int Instance; // ebx
  __int64 v6; // rdx
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v16; // [rsp+28h] [rbp-10h]

  v3 = a2 - 1;
  if ( !v3 )
  {
    *((_DWORD *)this + 64) = 0;
    Instance = RDPAPI_CreateInstance(0, &CLSID_RDPNsCodec, &IID_IRdpImageCompressor, (char *)this + 272);
    if ( Instance >= 0 )
    {
      Instance = RDPAPI_CreateInstance(0, &CLSID_RDPNsCodec, &IID_IRdpImageDecompressor, (char *)this + 280);
      if ( Instance >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v14);
      v8 = 29;
      v9 = "Failed To create Nscodec Decompressor";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13);
      v8 = 28;
      v9 = "Failed To create Nscodec Compressor";
    }
LABEL_38:
    v16 = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids,
      ActivityIdPrefix,
      (__int64)v9,
      v16);
    return (unsigned int)Instance;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    *((_DWORD *)this + 64) = 0;
    Instance = RDPAPI_CreateInstance(0, &CLSID_RDPPlanarCodec, &IID_IRdpImageCompressor, (char *)this + 272);
    if ( Instance >= 0 )
    {
      Instance = RDPAPI_CreateInstance(0, &CLSID_RDPPlanarCodec, &IID_IRdpImageDecompressor, (char *)this + 280);
      if ( Instance >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v12);
      v8 = 27;
      v9 = "Failed To create legacy Decompressor";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11);
      v8 = 26;
      v9 = "Failed To create legacy Compressor";
    }
    goto LABEL_38;
  }
  if ( v4 == 3 )
  {
    *((_DWORD *)this + 64) = 1;
    Instance = RDPAPI_CreateInstance(0, &CLSID_RDPCacImgCodec, &IID_IRdpImageCompressor, (char *)this + 272);
    if ( Instance >= 0 )
    {
      Instance = RDPAPI_CreateInstance(0, &CLSID_RDPCacImgCodec, &IID_IRdpImageDecompressor, (char *)this + 280);
      if ( Instance >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10);
      v8 = 31;
      v9 = "Failed To create CAC Decompressor";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Instance;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v6);
      v8 = 30;
      v9 = "Failed To create CAC Compressor";
    }
    goto LABEL_38;
  }
  Instance = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180081c98  mov     [rsp+arg_0], rbx
0x180081c9d  push    rdi
0x180081c9e  sub     rsp, 30h
0x180081ca2  mov     rdi, rcx
0x180081ca5  sub     edx, 1
0x180081ca8  jz      loc_180081EAD
0x180081cae  sub     edx, 1
0x180081cb1  jz      loc_180081DD7
0x180081cb7  cmp     edx, 3
0x180081cba  jz      short loc_180081D01
0x180081cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180081cc3  lea     rax, WPP_GLOBAL_Control
0x180081cca  xor     ebx, ebx
0x180081ccc  cmp     rcx, rax
0x180081ccf  jz      loc_180081F8E
0x180081cd5  test    byte ptr [rcx+1Ch], 1
0x180081cd9  jz      loc_180081F8E
0x180081cdf  cmp     byte ptr [rcx+19h], 1
0x180081ce3  jb      loc_180081F8E
0x180081ce9  mov     rcx, [rcx+10h]
0x180081ced  lea     edx, [rbx+20h]
0x180081cf0  lea     r8, WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids
0x180081cf7  call    WPP_SF_
0x180081cfc  jmp     loc_180081F8E
0x180081d01  mov     dword ptr [rcx+100h], 1
0x180081d0b  lea     r9, [rcx+110h]
0x180081d12  xor     ecx, ecx
0x180081d14  lea     r8, IID_IRdpImageCompressor
0x180081d1b  lea     rdx, CLSID_RDPCacImgCodec
0x180081d22  call    RDPAPI_CreateInstance
0x180081d27  mov     ebx, eax
0x180081d29  test    eax, eax
0x180081d2b  jns     short loc_180081D6F
0x180081d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d34  lea     rax, WPP_GLOBAL_Control
0x180081d3b  cmp     rcx, rax
0x180081d3e  jz      loc_180081F8E
0x180081d44  test    byte ptr [rcx+1Ch], 8
0x180081d48  jz      loc_180081F8E
0x180081d4e  cmp     byte ptr [rcx+19h], 2
0x180081d52  jb      loc_180081F8E
0x180081d58  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081d5e  mov     edx, 1Eh
0x180081d63  lea     rcx, aFailedToCreate_25; "Failed To create CAC Compressor"
0x180081d6a  jmp     loc_180081F6B
0x180081d6f  lea     r9, [rdi+118h]
0x180081d76  xor     ecx, ecx
0x180081d78  lea     r8, IID_IRdpImageDecompressor
0x180081d7f  lea     rdx, CLSID_RDPCacImgCodec
0x180081d86  call    RDPAPI_CreateInstance
0x180081d8b  mov     ebx, eax
0x180081d8d  test    eax, eax
0x180081d8f  jns     loc_180081F8E
0x180081d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d9c  lea     rax, WPP_GLOBAL_Control
0x180081da3  cmp     rcx, rax
0x180081da6  jz      loc_180081F8E
0x180081dac  test    byte ptr [rcx+1Ch], 8
0x180081db0  jz      loc_180081F8E
0x180081db6  cmp     byte ptr [rcx+19h], 2
0x180081dba  jb      loc_180081F8E
0x180081dc0  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081dc6  mov     edx, 1Fh
0x180081dcb  lea     rcx, aFailedToCreate_80; "Failed To create CAC Decompressor"
0x180081dd2  jmp     loc_180081F6B
0x180081dd7  mov     dword ptr [rcx+100h], 0
0x180081de1  lea     r9, [rcx+110h]
0x180081de8  xor     ecx, ecx
0x180081dea  lea     r8, IID_IRdpImageCompressor
0x180081df1  lea     rdx, CLSID_RDPPlanarCodec
0x180081df8  call    RDPAPI_CreateInstance
0x180081dfd  mov     ebx, eax
0x180081dff  test    eax, eax
0x180081e01  jns     short loc_180081E45
0x180081e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e0a  lea     rax, WPP_GLOBAL_Control
0x180081e11  cmp     rcx, rax
0x180081e14  jz      loc_180081F8E
0x180081e1a  test    byte ptr [rcx+1Ch], 8
0x180081e1e  jz      loc_180081F8E
0x180081e24  cmp     byte ptr [rcx+19h], 2
0x180081e28  jb      loc_180081F8E
0x180081e2e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081e34  mov     edx, 1Ah
0x180081e39  lea     rcx, aFailedToCreate_121; "Failed To create legacy Compressor"
0x180081e40  jmp     loc_180081F6B
0x180081e45  lea     r9, [rdi+118h]
0x180081e4c  xor     ecx, ecx
0x180081e4e  lea     r8, IID_IRdpImageDecompressor
0x180081e55  lea     rdx, CLSID_RDPPlanarCodec
0x180081e5c  call    RDPAPI_CreateInstance
0x180081e61  mov     ebx, eax
0x180081e63  test    eax, eax
0x180081e65  jns     loc_180081F8E
0x180081e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180081e72  lea     rax, WPP_GLOBAL_Control
0x180081e79  cmp     rcx, rax
0x180081e7c  jz      loc_180081F8E
0x180081e82  test    byte ptr [rcx+1Ch], 8
0x180081e86  jz      loc_180081F8E
0x180081e8c  cmp     byte ptr [rcx+19h], 2
0x180081e90  jb      loc_180081F8E
0x180081e96  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081e9c  mov     edx, 1Bh
0x180081ea1  lea     rcx, aFailedToCreate_10; "Failed To create legacy Decompressor"
0x180081ea8  jmp     loc_180081F6B
0x180081ead  mov     dword ptr [rcx+100h], 0
0x180081eb7  lea     r9, [rcx+110h]
0x180081ebe  xor     ecx, ecx
0x180081ec0  lea     r8, IID_IRdpImageCompressor
0x180081ec7  lea     rdx, CLSID_RDPNsCodec
0x180081ece  call    RDPAPI_CreateInstance
0x180081ed3  mov     ebx, eax
0x180081ed5  test    eax, eax
0x180081ed7  jns     short loc_180081F18
0x180081ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180081ee0  lea     rax, WPP_GLOBAL_Control
0x180081ee7  cmp     rcx, rax
0x180081eea  jz      loc_180081F8E
0x180081ef0  test    byte ptr [rcx+1Ch], 8
0x180081ef4  jz      loc_180081F8E
0x180081efa  cmp     byte ptr [rcx+19h], 2
0x180081efe  jb      loc_180081F8E
0x180081f04  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081f0a  mov     edx, 1Ch
0x180081f0f  lea     rcx, aFailedToCreate_27; "Failed To create Nscodec Compressor"
0x180081f16  jmp     short loc_180081F6B
0x180081f18  lea     r9, [rdi+118h]
0x180081f1f  xor     ecx, ecx
0x180081f21  lea     r8, IID_IRdpImageDecompressor
0x180081f28  lea     rdx, CLSID_RDPNsCodec
0x180081f2f  call    RDPAPI_CreateInstance
0x180081f34  mov     ebx, eax
0x180081f36  test    eax, eax
0x180081f38  jns     short loc_180081F8E
0x180081f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f41  lea     rax, WPP_GLOBAL_Control
0x180081f48  cmp     rcx, rax
0x180081f4b  jz      short loc_180081F8E
0x180081f4d  test    byte ptr [rcx+1Ch], 8
0x180081f51  jz      short loc_180081F8E
0x180081f53  cmp     byte ptr [rcx+19h], 2
0x180081f57  jb      short loc_180081F8E
0x180081f59  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180081f5f  mov     edx, 1Dh
0x180081f64  lea     rcx, aFailedToCreate_90; "Failed To create Nscodec Decompressor"
0x180081f6b  mov     [rsp+38h+var_10], ebx
0x180081f6f  lea     r8, WPP_3bc4f7a008033dad978d3452ef221b55_Traceguids
0x180081f76  mov     [rsp+38h+var_18], rcx
0x180081f7b  mov     r9d, eax
0x180081f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081f85  mov     rcx, [rcx+10h]
0x180081f89  call    WPP_SF_DsD
0x180081f8e  mov     eax, ebx
0x180081f90  mov     rbx, [rsp+38h+arg_0]
0x180081f95  add     rsp, 30h
0x180081f99  pop     rdi
0x180081f9a  retn
```
