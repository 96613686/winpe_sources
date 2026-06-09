# CertPolEngProvider::GenericMethodFailure<char const * &,long &>(char const * &,long &)

- ea: `0x180003e60`
- end: `0x180003fa1`
- name: `??$GenericMethodFailure@AEAPEBDAEAJ@CertPolEngProvider@@SAXAEAPEBDAEAJ@Z`
- size: `321`
- prototype: `__int64 __fastcall(const unsigned __int16 **, _DWORD *)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001d90`
- `0x180002560`
- `0x180003000`
- `0x1800030f0`
- `0x180003dc0`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800058e0`
- `0x180005b30`
- `0x180005c20`
- `0x180006600`

## callees

- `0x180003e60`
- `0x180008200`
- `0x18001a380`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180003f7a`
- `ntdll!EtwEventWriteTransfer` at `0x180003f7a`

## pseudocode

```c
__int64 __fastcall CertPolEngProvider::GenericMethodFailure<char const * &,long &>(
        const unsigned __int16 **a1,
        _DWORD *a2)
{
  unsigned int *v4; // r10
  __int64 result; // rax
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // [rsp+30h] [rbp-78h] BYREF
  _DWORD v10[2]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v11; // [rsp+40h] [rbp-68h]
  unsigned __int16 *v12; // [rsp+50h] [rbp-58h] BYREF
  int v13; // [rsp+58h] [rbp-50h]
  int v14; // [rsp+5Ch] [rbp-4Ch]
  char *v15; // [rsp+60h] [rbp-48h]
  int v16; // [rsp+68h] [rbp-40h]
  int v17; // [rsp+6Ch] [rbp-3Ch]
  const unsigned __int16 *v18; // [rsp+70h] [rbp-38h]
  int v19; // [rsp+78h] [rbp-30h]
  int v20; // [rsp+7Ch] [rbp-2Ch]
  __int64 *v21; // [rsp+80h] [rbp-28h]
  __int64 v22; // [rsp+88h] [rbp-20h]

  v4 = (unsigned int *)*((_QWORD *)CertPolEngProvider::Instance() + 1);
  result = *v4;
  if ( (unsigned int)result > 5 )
  {
    v6 = *a1;
    LODWORD(v9) = *a2;
    v21 = &v9;
    v22 = 4;
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_BYTE *)v6 + v7) );
      v8 = v7 + 1;
    }
    else
    {
      v6 = &dword_18001E424;
      v8 = 1;
    }
    v19 = v8;
    v10[1] = 5;
    v12 = (unsigned __int16 *)*((_QWORD *)v4 + 1);
    v18 = v6;
    v20 = 0;
    v11 = 0;
    v10[0] = 184549376;
    v13 = *v12;
    v15 = byte_180023665;
    v14 = 2;
    v16 = 40;
    v17 = 1;
    HIDWORD(v9) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return ((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD, int, unsigned __int16 **, __int64))EtwEventWriteTransfer)(
             *((_QWORD *)v4 + 4),
             v10,
             0,
             0,
             4,
             &v12,
             v9);
  }
  return result;
}

```

## disassembly

```asm
0x180003e60  mov     [rsp+arg_0], rbx
0x180003e65  push    rdi
0x180003e66  sub     rsp, 0A0h
0x180003e6d  mov     rax, cs:__security_cookie
0x180003e74  xor     rax, rsp
0x180003e77  mov     [rsp+0A8h+var_18], rax
0x180003e7f  mov     rbx, rdx
0x180003e82  mov     rdi, rcx
0x180003e85  call    ?Instance@CertPolEngProvider@@KAPEAV1@XZ; CertPolEngProvider::Instance(void)
0x180003e8a  mov     r10, [rax+8]
0x180003e8e  mov     eax, [r10]
0x180003e91  cmp     eax, 5
0x180003e94  jbe     loc_180003F80
0x180003e9a  mov     eax, [rbx]
0x180003e9c  xor     edx, edx
0x180003e9e  mov     rcx, [rdi]
0x180003ea1  mov     [rsp+0A8h+var_78], eax
0x180003ea5  lea     rax, [rsp+0A8h+var_78]
0x180003eaa  mov     [rsp+0A8h+var_28], rax
0x180003eb2  mov     [rsp+0A8h+var_20], 4
0x180003ebe  test    rcx, rcx
0x180003ec1  jz      short loc_180003EDC
0x180003ec3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003eca  nop     word ptr [rax+rax+00h]
0x180003ed0  inc     rax
0x180003ed3  cmp     [rcx+rax], dl
0x180003ed6  jnz     short loc_180003ED0
0x180003ed8  inc     eax
0x180003eda  jmp     short loc_180003EE8
0x180003edc  lea     rcx, dword_18001E424
0x180003ee3  mov     eax, 1
0x180003ee8  mov     [rsp+0A8h+var_30], eax
0x180003eec  xor     r9d, r9d
0x180003eef  movzx   eax, cs:word_18002365B
0x180003ef6  xor     r8d, r8d
0x180003ef9  mov     [rsp+0A8h+var_6C], eax
0x180003efd  mov     rax, [r10+8]
0x180003f01  mov     [rsp+0A8h+var_58], rax
0x180003f06  mov     [rsp+0A8h+var_38], rcx
0x180003f0b  lea     rcx, _TraceLoggingMetadata
0x180003f12  mov     [rsp+0A8h+var_2C], edx
0x180003f16  mov     [rsp+0A8h+var_68], rdx
0x180003f1b  lea     rdx, [rsp+0A8h+var_70]
0x180003f20  mov     [rsp+0A8h+var_70], 0B000000h
0x180003f28  movzx   eax, word ptr [rax]
0x180003f2b  mov     [rsp+0A8h+var_50], eax
0x180003f2f  lea     rax, byte_180023665
0x180003f36  mov     [rsp+0A8h+var_48], rax
0x180003f3b  lea     rax, _TraceLoggingMetadataEnd
0x180003f42  sub     eax, ecx
0x180003f44  mov     [rsp+0A8h+var_4C], 2
0x180003f4c  mov     [rsp+0A8h+var_40], 28h ; '('
0x180003f54  mov     [rsp+0A8h+var_3C], 1
0x180003f5c  mov     [rsp+0A8h+var_74], eax
0x180003f60  mov     eax, [rsp+0A8h+var_74]
0x180003f64  mov     rcx, [r10+20h]
0x180003f68  lea     rax, [rsp+0A8h+var_58]
0x180003f6d  mov     [rsp+0A8h+var_80], rax
0x180003f72  mov     [rsp+0A8h+var_88], 4
0x180003f7a  call    cs:__imp_EtwEventWriteTransfer
0x180003f80  mov     rcx, [rsp+0A8h+var_18]
0x180003f88  xor     rcx, rsp; StackCookie
0x180003f8b  call    __security_check_cookie
0x180003f90  mov     rbx, [rsp+0A8h+arg_0]
0x180003f98  add     rsp, 0A0h
0x180003f9f  pop     rdi
0x180003fa0  retn
```
