# Common::Deployment::GetSignatureStreamFromPackageRoot(ushort const *,IStream * *)

- ea: `0x18004c428`
- end: `0x18004c55c`
- name: `?GetSignatureStreamFromPackageRoot@Deployment@Common@@YAJPEBGPEAPEAUIStream@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *, struct IStream **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043130`

## callees

- `0x180004920`
- `0x180010384`
- `0x180018248`
- `0x18001ca24`
- `0x18004682c`
- `0x18004c428`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c4d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004c4d0`

## string_xrefs

- `0x18004c48d`: `onecore\admin\appmodel\common\signaturetools.cpp`
- `0x18004c4e5`: `onecore\admin\appmodel\common\signaturetools.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetSignatureStreamFromPackageRoot(
        Common::Deployment *this,
        const unsigned __int16 *a2,
        struct IStream **a3)
{
  int v3; // eax
  bool *v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  Common *v12[2]; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  LPVOID v15; // [rsp+78h] [rbp+18h] BYREF

  *(_QWORD *)a2 = 0;
  v13 = 0;
  *(_OWORD *)v12 = 0;
  v3 = Common::PathHelpers::CombinePaths(
         (const unsigned __int16 *)this,
         L"AppxSignature.p7x",
         (struct Common::StringBuffer *)v12);
  v5 = v3;
  if ( v3 >= 0 )
  {
    LOBYTE(v15) = 0;
    v3 = Common::FileExists(v12[1], (const unsigned __int16 *)&v15, v4);
    v5 = v3;
    if ( v3 < 0 )
    {
      v6 = 35;
      goto LABEL_5;
    }
    if ( (_BYTE)v15 )
    {
      v15 = 0;
      v7 = CoCreateInstance(
             &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
             0,
             1u,
             &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
             &v15);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 44;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\admin\\appmodel\\common\\signaturetools.cpp",
          (const char *)(unsigned int)v7,
          ppva);
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v15);
        goto LABEL_14;
      }
      ppva = 128;
      v7 = (*(__int64 (__fastcall **)(LPVOID, Common *, __int64))(*(_QWORD *)v15 + 40LL))(v15, v12[1], 1);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 51;
        goto LABEL_9;
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v15);
    }
    v5 = 0;
    goto LABEL_14;
  }
  v6 = 32;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\admin\\appmodel\\common\\signaturetools.cpp",
    (const char *)(unsigned int)v3,
    ppv);
LABEL_14:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v12);
  return v5;
}

```

## disassembly

```asm
0x18004c428  mov     [rsp-8+arg_0], rbx
0x18004c42d  mov     [rsp-8+arg_10], rdi
0x18004c432  push    rbp
0x18004c433  mov     rbp, rsp
0x18004c436  sub     rsp, 60h
0x18004c43a  mov     rdi, rdx
0x18004c43d  mov     qword ptr [rdx], 0
0x18004c444  xor     eax, eax
0x18004c446  lea     rdx, aAppxsignatureP; "AppxSignature.p7x"
0x18004c44d  xorps   xmm0, xmm0
0x18004c450  mov     [rbp+var_10], eax
0x18004c453  lea     r8, [rbp+var_20]; this
0x18004c457  movups  xmmword ptr [rbp+var_20], xmm0
0x18004c45b  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18004c460  mov     ebx, eax
0x18004c462  test    eax, eax
0x18004c464  jns     short loc_18004C46D
0x18004c466  mov     edx, 20h ; ' '
0x18004c46b  jmp     short loc_18004C489
0x18004c46d  mov     rcx, [rbp+var_20+8]; this
0x18004c471  lea     rdx, [rbp+arg_8]; unsigned __int16 *
0x18004c475  mov     byte ptr [rbp+arg_8], 0
0x18004c479  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x18004c47e  mov     ebx, eax
0x18004c480  test    eax, eax
0x18004c482  jns     short loc_18004C4A1
0x18004c484  mov     edx, 23h ; '#'; void *
0x18004c489  mov     rcx, [rbp+8]; this
0x18004c48d  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\common\\signa"...
0x18004c494  mov     r9d, eax; char *
0x18004c497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c49c  jmp     loc_18004C53F
0x18004c4a1  cmp     byte ptr [rbp+arg_8], 0
0x18004c4a5  jz      loc_18004C53D
0x18004c4ab  xor     edx, edx; pUnkOuter
0x18004c4ad  mov     [rbp+arg_8], 0
0x18004c4b5  lea     rax, [rbp+arg_8]
0x18004c4b9  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x18004c4c0  mov     [rsp+60h+ppv], rax; int
0x18004c4c5  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x18004c4cc  lea     r8d, [rdx+1]; dwClsContext
0x18004c4d0  call    cs:__imp_CoCreateInstance
0x18004c4d6  mov     ebx, eax
0x18004c4d8  test    eax, eax
0x18004c4da  jns     short loc_18004C4FF
0x18004c4dc  mov     edx, 2Ch ; ','; void *
0x18004c4e1  mov     rcx, [rbp+8]; this
0x18004c4e5  lea     r8, aOnecoreAdminAp_15; "onecore\\admin\\appmodel\\common\\signa"...
0x18004c4ec  mov     r9d, eax; char *
0x18004c4ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c4f4  lea     rcx, [rbp+arg_8]
0x18004c4f8  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c4fd  jmp     short loc_18004C53F
0x18004c4ff  mov     rcx, [rbp+arg_8]
0x18004c503  xor     r9d, r9d
0x18004c506  mov     rdx, [rbp+var_20+8]
0x18004c50a  mov     [rsp+60h+var_38], rdi
0x18004c50f  mov     dword ptr [rsp+60h+ppv], 80h
0x18004c517  mov     rax, [rcx]
0x18004c51a  lea     r8d, [r9+1]
0x18004c51e  mov     rax, [rax+28h]
0x18004c522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c527  mov     ebx, eax
0x18004c529  test    eax, eax
0x18004c52b  jns     short loc_18004C534
0x18004c52d  mov     edx, 33h ; '3'
0x18004c532  jmp     short loc_18004C4E1
0x18004c534  lea     rcx, [rbp+arg_8]
0x18004c538  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004c53d  xor     ebx, ebx
0x18004c53f  lea     rcx, [rbp+var_20]; this
0x18004c543  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004c548  lea     r11, [rsp+60h+var_s0]
0x18004c54d  mov     eax, ebx
0x18004c54f  mov     rbx, [r11+10h]
0x18004c553  mov     rdi, [r11+20h]
0x18004c557  mov     rsp, r11
0x18004c55a  pop     rbp
0x18004c55b  retn
```
