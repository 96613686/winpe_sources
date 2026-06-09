# PstMapCertificate

- ea: `0x180013ac0`
- end: `0x180013b3d`
- name: `PstMapCertificate`
- size: `125`
- prototype: `NTSTATUS __stdcall(PCCERT_CONTEXT pCert, LSA_TOKEN_INFORMATION_TYPE *pTokenInformationType, PVOID *ppTokenInformation)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003dc0`
- `0x180007ea0`
- `0x180013ac0`
- `0x18001640c`

## pseudocode

```c
NTSTATUS __stdcall PstMapCertificate(
        PCCERT_CONTEXT pCert,
        LSA_TOKEN_INFORMATION_TYPE *pTokenInformationType,
        PVOID *ppTokenInformation)
{
  CProviderRegistrationCache *v6; // rcx
  NTSTATUS v7; // ebx
  _BYTE v9[40]; // [rsp+30h] [rbp-28h] BYREF
  NTSTATUS v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  CLogETWBlock::CLogETWBlock((CLogETWBlock *)v9, "PstMapCertificate", (int *)ppTokenInformation, &v10, 0);
  if ( g_pProvRegCache )
    v7 = CProviderRegistrationCache::MapCertificate(v6, pCert, pTokenInformationType, ppTokenInformation);
  else
    v7 = -1073741595;
  v10 = v7;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v9);
  return v7;
}

```

## disassembly

```asm
0x180013ac0  mov     rax, rsp
0x180013ac3  mov     [rax+8], rbx
0x180013ac7  mov     [rax+10h], rsi
0x180013acb  push    rdi
0x180013acc  sub     rsp, 50h
0x180013ad0  mov     rdi, rdx
0x180013ad3  mov     dword ptr [rax+20h], 0
0x180013ada  mov     rsi, rcx
0x180013add  mov     qword ptr [rax-38h], 0
0x180013ae5  lea     rdx, aPstmapcertific_0; "PstMapCertificate"
0x180013aec  mov     rbx, r8
0x180013aef  lea     rcx, [rax-28h]; this
0x180013af3  lea     r9, [rax+20h]; int *
0x180013af7  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180013afc  cmp     cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA, 0; CProviderRegistrationCache * g_pProvRegCache
0x180013b04  jz      short loc_180013B18
0x180013b06  mov     r9, rbx; void **
0x180013b09  mov     r8, rdi; enum _LSA_TOKEN_INFORMATION_TYPE *
0x180013b0c  mov     rdx, rsi; struct _CERT_CONTEXT *
0x180013b0f  call    ?MapCertificate@CProviderRegistrationCache@@QEAAJPEBU_CERT_CONTEXT@@PEAW4_LSA_TOKEN_INFORMATION_TYPE@@PEAPEAX@Z; CProviderRegistrationCache::MapCertificate(_CERT_CONTEXT const *,_LSA_TOKEN_INFORMATION_TYPE *,void * *)
0x180013b14  mov     ebx, eax
0x180013b16  jmp     short loc_180013B1D
0x180013b18  mov     ebx, 0C00000E5h
0x180013b1d  lea     rcx, [rsp+58h+var_28]; this
0x180013b22  mov     [rsp+58h+arg_18], ebx
0x180013b26  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180013b2b  mov     rsi, [rsp+58h+arg_8]
0x180013b30  mov     eax, ebx
0x180013b32  mov     rbx, [rsp+58h+arg_0]
0x180013b37  add     rsp, 50h
0x180013b3b  pop     rdi
0x180013b3c  retn
```
