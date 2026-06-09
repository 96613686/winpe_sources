# CDriveConfiguration::Initialize(_BDECFG_PARAMS const *,_BDECFG_SIZE_REQUIREMENTS * const,IConfigurationProgress *)

- ea: `0x18000fa80`
- end: `0x18000faf7`
- name: `?Initialize@CDriveConfiguration@@QEAAJPEBU_BDECFG_PARAMS@@QEAU_BDECFG_SIZE_REQUIREMENTS@@PEAVIConfigurationProgress@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(CDriveConfiguration *__hidden this, const struct _BDECFG_PARAMS *, struct _BDECFG_SIZE_REQUIREMENTS *const, struct IConfigurationProgress *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000fa80`

## import_xrefs

- `msvcrt!_beginthread` at `0x18000fae2`
- `msvcrt!_beginthread` at `0x18000fae2`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::Initialize(
        CDriveConfiguration *this,
        const struct _BDECFG_PARAMS *a2,
        struct _BDECFG_SIZE_REQUIREMENTS *const a3,
        struct IConfigurationProgress *a4)
{
  unsigned int v4; // ebx

  v4 = 0;
  if ( a2 && a3 && a4 )
  {
    *(_OWORD *)((char *)this + 1176) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + 1192) = *((_OWORD *)a2 + 1);
    *(_OWORD *)((char *)this + 1208) = *(_OWORD *)a3;
    *(_OWORD *)((char *)this + 1224) = *((_OWORD *)a3 + 1);
    *(_OWORD *)((char *)this + 1240) = *((_OWORD *)a3 + 2);
    *((_QWORD *)this + 157) = a4;
    _beginthread(CDriveConfiguration::InitializeEntry, 0, this);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x18000fa80  push    rbx
0x18000fa82  sub     rsp, 20h
0x18000fa86  xor     ebx, ebx
0x18000fa88  test    rdx, rdx
0x18000fa8b  jz      short loc_18000FAEA
0x18000fa8d  test    r8, r8
0x18000fa90  jz      short loc_18000FAEA
0x18000fa92  test    r9, r9
0x18000fa95  jz      short loc_18000FAEA
0x18000fa97  movups  xmm0, xmmword ptr [rdx]
0x18000fa9a  movups  xmmword ptr [rcx+498h], xmm0
0x18000faa1  movups  xmm1, xmmword ptr [rdx+10h]
0x18000faa5  movups  xmmword ptr [rcx+4A8h], xmm1
0x18000faac  movups  xmm0, xmmword ptr [r8]
0x18000fab0  movups  xmmword ptr [rcx+4B8h], xmm0
0x18000fab7  movups  xmm1, xmmword ptr [r8+10h]
0x18000fabc  movups  xmmword ptr [rcx+4C8h], xmm1
0x18000fac3  movups  xmm0, xmmword ptr [r8+20h]
0x18000fac8  movups  xmmword ptr [rcx+4D8h], xmm0
0x18000facf  mov     [rcx+4E8h], r9
0x18000fad6  mov     r8, rcx; ArgList
0x18000fad9  xor     edx, edx; StackSize
0x18000fadb  lea     rcx, ?InitializeEntry@CDriveConfiguration@@CAXPEAX@Z; StartAddress
0x18000fae2  call    cs:__imp__beginthread
0x18000fae8  jmp     short loc_18000FAEF
0x18000faea  mov     ebx, 80004003h
0x18000faef  mov     eax, ebx
0x18000faf1  add     rsp, 20h
0x18000faf5  pop     rbx
0x18000faf6  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
