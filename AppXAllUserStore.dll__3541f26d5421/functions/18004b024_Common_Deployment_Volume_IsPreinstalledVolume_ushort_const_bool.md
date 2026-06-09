# Common::Deployment::Volume::IsPreinstalledVolume(ushort const *,bool *)

- ea: `0x18004b024`
- end: `0x18004b0f7`
- name: `?IsPreinstalledVolume@Volume@Deployment@Common@@SAJPEBGPEA_N@Z`
- size: `211`
- prototype: `__int64 __fastcall(LPCWCH lpString1, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015ff0`

## callees

- `0x180004920`
- `0x180007278`
- `0x180018248`
- `0x1800493a4`
- `0x18004b024`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004b0cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004b0cd`

## string_xrefs

- `0x18004b055`: `onecore\admin\appmodel\common\volume.cpp`
- `0x18004b097`: `onecore\admin\appmodel\common\volume.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::Volume::IsPreinstalledVolume(LPCWCH lpString1, bool *a2)
{
  int IsStateSeparationEnabled; // eax
  struct Common::StringBuffer *v5; // rdx
  unsigned int v6; // ebx
  int PreInstalledSisFullPath; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  LPCWCH lpString2[2]; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  bool v13; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  v13 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v13);
  v6 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volume.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      bIgnoreCase);
    return v6;
  }
  if ( v13 )
  {
    v11 = 0;
    *(_OWORD *)lpString2 = 0;
    PreInstalledSisFullPath = Common::Deployment::Configuration::GetPreInstalledSisFullPath(
                                (Common::Deployment::Configuration *)lpString2,
                                v5);
    v6 = PreInstalledSisFullPath;
    if ( PreInstalledSisFullPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\admin\\appmodel\\common\\volume.cpp",
        (const char *)(unsigned int)PreInstalledSisFullPath,
        bIgnoreCase);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString2);
      return v6;
    }
    *a2 = CompareStringOrdinal(lpString1, -1, lpString2[1], -1, 1) == 2;
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpString2);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b024  mov     rax, rsp
0x18004b027  mov     [rax+8], rbx
0x18004b02b  mov     [rax+18h], rsi
0x18004b02f  push    rdi
0x18004b030  sub     rsp, 50h
0x18004b034  mov     rsi, rcx
0x18004b037  mov     byte ptr [rdx], 0
0x18004b03a  lea     rcx, [rax+10h]; bool *
0x18004b03e  mov     byte ptr [rax+10h], 0
0x18004b042  mov     rdi, rdx
0x18004b045  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18004b04a  mov     ebx, eax
0x18004b04c  test    eax, eax
0x18004b04e  jns     short loc_18004B06D
0x18004b050  mov     rcx, [rsp+58h]; this
0x18004b055  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\volum"...
0x18004b05c  mov     r9d, eax; char *
0x18004b05f  mov     edx, 0B0h; void *
0x18004b064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b069  mov     eax, ebx
0x18004b06b  jmp     short loc_18004B0E7
0x18004b06d  cmp     [rsp+58h+arg_8], 0
0x18004b072  jz      short loc_18004B0E5
0x18004b074  xor     eax, eax
0x18004b076  lea     rcx, [rsp+58h+lpString2]; this
0x18004b07b  xorps   xmm0, xmm0
0x18004b07e  mov     [rsp+58h+var_18], eax
0x18004b082  movups  xmmword ptr [rsp+58h+lpString2], xmm0
0x18004b087  call    ?GetPreInstalledSisFullPath@Configuration@Deployment@Common@@YAJPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetPreInstalledSisFullPath(Common::StringBuffer *)
0x18004b08c  mov     ebx, eax
0x18004b08e  test    eax, eax
0x18004b090  jns     short loc_18004B0B7
0x18004b092  mov     rcx, [rsp+58h]; this
0x18004b097  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\volum"...
0x18004b09e  mov     r9d, eax; char *
0x18004b0a1  mov     edx, 0B4h; void *
0x18004b0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b0ab  lea     rcx, [rsp+58h+lpString2]; this
0x18004b0b0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004b0b5  jmp     short loc_18004B069
0x18004b0b7  mov     r8, [rsp+58h+lpString2+8]; lpString2
0x18004b0bc  or      edx, 0FFFFFFFFh; cchCount1
0x18004b0bf  mov     r9d, edx; cchCount2
0x18004b0c2  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18004b0ca  mov     rcx, rsi; lpString1
0x18004b0cd  call    cs:__imp_CompareStringOrdinal
0x18004b0d3  cmp     eax, 2
0x18004b0d6  setz    cl
0x18004b0d9  mov     [rdi], cl
0x18004b0db  lea     rcx, [rsp+58h+lpString2]; this
0x18004b0e0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004b0e5  xor     eax, eax
0x18004b0e7  mov     rbx, [rsp+58h+arg_0]
0x18004b0ec  mov     rsi, [rsp+58h+arg_10]
0x18004b0f1  add     rsp, 50h
0x18004b0f5  pop     rdi
0x18004b0f6  retn
```
