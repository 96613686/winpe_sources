# CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)

- ea: `0x18001764c`
- end: `0x1800176b9`
- name: `?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z`
- size: `109`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016ab8`

## callees

- `0x18000f9d0`
- `0x18001764c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001767c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001767c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800176a8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800176a8`

## pseudocode

```c
__int64 __fastcall CameraGenerateDWORD64Hash(PUCHAR pbInput, ULONG cbInput, unsigned __int64 *a3)
{
  NTSTATUS DWORD64HashWithHandle; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp+20h] BYREF

  phAlgorithm = 0;
  DWORD64HashWithHandle = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( DWORD64HashWithHandle >= 0 )
    DWORD64HashWithHandle = CameraGenerateDWORD64HashWithHandle(pbInput, cbInput, phAlgorithm, a3);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)DWORD64HashWithHandle;
}

```

## disassembly

```asm
0x18001764c  push    rbx
0x18001764e  push    rbp
0x18001764f  push    rsi
0x180017650  push    rdi
0x180017651  sub     rsp, 28h
0x180017655  mov     rdi, r8
0x180017658  mov     [rsp+48h+phAlgorithm], 0
0x180017661  mov     esi, edx
0x180017663  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18001766a  mov     rbp, rcx
0x18001766d  lea     rdx, pszAlgId; "SHA256"
0x180017674  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x180017679  xor     r9d, r9d; dwFlags
0x18001767c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180017682  mov     ebx, eax
0x180017684  test    eax, eax
0x180017686  js      short loc_18001769C
0x180017688  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x18001768d  mov     r9, rdi; unsigned __int64 *
0x180017690  mov     edx, esi; cbInput
0x180017692  mov     rcx, rbp; pbInput
0x180017695  call    ?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z; CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)
0x18001769a  mov     ebx, eax
0x18001769c  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x1800176a1  test    rcx, rcx
0x1800176a4  jz      short loc_1800176AE
0x1800176a6  xor     edx, edx; dwFlags
0x1800176a8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800176ae  mov     eax, ebx
0x1800176b0  add     rsp, 28h
0x1800176b4  pop     rdi
0x1800176b5  pop     rsi
0x1800176b6  pop     rbp
0x1800176b7  pop     rbx
0x1800176b8  retn
```
