# GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)

- ea: `0x18004128c`
- end: `0x180041416`
- name: `?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z`
- size: `394`
- prototype: `int(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned int *)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180040dc4`
- `0x1800414c4`
- `0x180041728`
- `0x180041914`
- `0x180041cf4`
- `0x180042080`

## callees

- `0x180007894`
- `0x180007900`
- `0x1800085d4`
- `0x18004128c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180041300`
- `ntdll!RtlNtStatusToDosError` at `0x180041300`
- `bcrypt!BCryptCreateHash` at `0x18004138f`
- `bcrypt!BCryptCreateHash` at `0x18004138f`
- `bcrypt!BCryptHashData` at `0x1800413aa`
- `bcrypt!BCryptHashData` at `0x1800413aa`
- `bcrypt!BCryptDestroyHash` at `0x1800413e0`
- `bcrypt!BCryptDestroyHash` at `0x1800413e0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800413fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800413fe`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800412f4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800412f4`
- `bcrypt!BCryptGetProperty` at `0x180041344`
- `bcrypt!BCryptGetProperty` at `0x180041344`
- `bcrypt!BCryptFinishHash` at `0x1800413c7`
- `bcrypt!BCryptFinishHash` at `0x1800413c7`

## pseudocode

```c
__int64 __fastcall GenerateOfflineDeviceID(
        __int64 a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  bool v8; // cf
  unsigned int v9; // ebx
  void *v10; // rdi
  int Property; // eax
  signed int v12; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  ULONG pbOutput; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int8 *pcbResult; // [rsp+78h] [rbp+28h] BYREF

  pcbResult = a2;
  phAlgorithm = 0;
  phHash = 0;
  pbOutput = 0;
  v8 = *a6 < 0x20;
  LODWORD(pcbResult) = 0;
  if ( v8 )
  {
    *a6 = 32;
    return (unsigned int)-2147024774;
  }
  else
  {
    v10 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
    if ( Property < 0
      || (LODWORD(pcbResult) = 4,
          Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0),
          Property < 0)
      || (v10 = operator new(pbOutput),
          memset_0(v10, 0, pbOutput),
          Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v10, pbOutput, 0, 0, 0),
          Property < 0)
      || (Property = BCryptHashData(phHash, a4, a3, 0), Property < 0)
      || (Property = BCryptFinishHash(phHash, a5, 0x20u, 0), Property < 0) )
    {
      v12 = RtlNtStatusToDosError(Property);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v9 = 0;
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( v10 )
      operator delete(v10);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x18004128c  mov     [rsp-18h+arg_10], rbx
0x180041291  mov     [rsp-18h+arg_8], rdx
0x180041296  mov     [rsp-18h+pbOutput], ecx
0x18004129a  push    rbp
0x18004129b  push    rsi
0x18004129c  push    rdi
0x18004129d  mov     rbp, rsp
0x1800412a0  sub     rsp, 50h
0x1800412a4  mov     rax, [rbp+arg_28]
0x1800412a8  mov     rbx, r9
0x1800412ab  mov     esi, r8d
0x1800412ae  mov     [rbp+phAlgorithm], 0
0x1800412b6  mov     [rbp+phHash], 0
0x1800412be  mov     [rbp+pbOutput], 0
0x1800412c5  cmp     dword ptr [rax], 20h ; ' '
0x1800412c8  mov     dword ptr [rbp+arg_8], 0
0x1800412cf  jnb     short loc_1800412E1
0x1800412d1  mov     dword ptr [rax], 20h ; ' '
0x1800412d7  mov     ebx, 8007007Ah
0x1800412dc  jmp     loc_180041404
0x1800412e1  xor     r9d, r9d; dwFlags
0x1800412e4  lea     rdx, pszAlgId; "SHA256"
0x1800412eb  xor     r8d, r8d; pszImplementation
0x1800412ee  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800412f2  xor     edi, edi
0x1800412f4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800412fa  test    eax, eax
0x1800412fc  jns     short loc_18004131E
0x1800412fe  mov     ecx, eax; Status
0x180041300  call    cs:__imp_RtlNtStatusToDosError
0x180041306  mov     ebx, eax
0x180041308  test    eax, eax
0x18004130a  jle     loc_1800413D7
0x180041310  movzx   ebx, ax
0x180041313  or      ebx, 80070000h
0x180041319  jmp     loc_1800413D7
0x18004131e  mov     rcx, [rbp+phAlgorithm]; hObject
0x180041322  lea     rax, [rbp+arg_8]
0x180041326  mov     r9d, 4; cbOutput
0x18004132c  mov     [rsp+50h+dwFlags], edi; dwFlags
0x180041330  lea     r8, [rbp+pbOutput]; pbOutput
0x180041334  mov     dword ptr [rbp+arg_8], r9d
0x180041338  lea     rdx, aObjectlength; "ObjectLength"
0x18004133f  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180041344  call    cs:__imp_BCryptGetProperty
0x18004134a  test    eax, eax
0x18004134c  js      short loc_1800412FE
0x18004134e  mov     ecx, [rbp+pbOutput]; Size
0x180041351  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041356  mov     r8d, [rbp+pbOutput]; Size
0x18004135a  xor     edx, edx; Val
0x18004135c  mov     rcx, rax; void *
0x18004135f  mov     rdi, rax
0x180041362  call    memset_0
0x180041367  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18004136b  lea     rdx, [rbp+phHash]; phHash
0x18004136f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180041373  mov     r8, rdi; pbHashObject
0x180041376  mov     [rsp+50h+var_20], 0; dwFlags
0x18004137e  mov     [rsp+50h+dwFlags], 0; cbSecret
0x180041386  mov     [rsp+50h+pcbResult], 0; pbSecret
0x18004138f  call    cs:__imp_BCryptCreateHash
0x180041395  test    eax, eax
0x180041397  js      loc_1800412FE
0x18004139d  mov     rcx, [rbp+phHash]; hHash
0x1800413a1  xor     r9d, r9d; dwFlags
0x1800413a4  mov     r8d, esi; cbInput
0x1800413a7  mov     rdx, rbx; pbInput
0x1800413aa  call    cs:__imp_BCryptHashData
0x1800413b0  test    eax, eax
0x1800413b2  js      loc_1800412FE
0x1800413b8  mov     rdx, [rbp+arg_20]; pbOutput
0x1800413bc  xor     r9d, r9d; dwFlags
0x1800413bf  mov     rcx, [rbp+phHash]; hHash
0x1800413c3  lea     r8d, [r9+20h]; cbOutput
0x1800413c7  call    cs:__imp_BCryptFinishHash
0x1800413cd  test    eax, eax
0x1800413cf  js      loc_1800412FE
0x1800413d5  xor     ebx, ebx
0x1800413d7  mov     rcx, [rbp+phHash]; hHash
0x1800413db  test    rcx, rcx
0x1800413de  jz      short loc_1800413E6
0x1800413e0  call    cs:__imp_BCryptDestroyHash
0x1800413e6  test    rdi, rdi
0x1800413e9  jz      short loc_1800413F3
0x1800413eb  mov     rcx, rdi; Block
0x1800413ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800413f3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800413f7  test    rcx, rcx
0x1800413fa  jz      short loc_180041404
0x1800413fc  xor     edx, edx; dwFlags
0x1800413fe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180041404  mov     eax, ebx
0x180041406  mov     rbx, [rsp+50h+arg_10]
0x18004140e  add     rsp, 50h
0x180041412  pop     rdi
0x180041413  pop     rsi
0x180041414  pop     rbp
0x180041415  retn
```
