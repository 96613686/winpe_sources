# BCryptIumOpenAlgorithmProvider

- ea: `0x140010cd0`
- end: `0x140010ed7`
- name: `BCryptIumOpenAlgorithmProvider`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140002080`
- `0x140007e00`
- `0x1400083a8`
- `0x14000a430`
- `0x14000a970`
- `0x140010cd0`
- `0x140011964`
- `0x140011ed4`
- `0x140011f58`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140010dcf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140010dcf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140010e26`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140010e26`

## pseudocode

```c
__int64 __fastcall BCryptIumOpenAlgorithmProvider(__int64 a1, _QWORD *a2, const WCHAR *a3, __int64 a4, ULONG dwFlags)
{
  const wchar_t *v8; // r9
  int v9; // r8d
  PVOID *v10; // r11
  unsigned int v11; // ebx
  NTSTATUS Context; // eax
  __int64 v13; // rdx
  struct _BCRYPT_ISO_OBJECT *BCryptIsoObject; // rax
  struct _BCRYPT_ISO_OBJECT *v15; // rdi
  int v16; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp-48h] BYREF
  struct BCRYPTIUM_CONTEXT *v19; // [rsp+38h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LODWORD(v8) = (_DWORD)a3;
    if ( !a3 )
      v8 = L"(null)";
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)v8, dwFlags);
  }
  if ( (unsigned int)IsKeyGuardSupportedAlgorithmName(a3) )
  {
    v19 = 0;
    Context = BCryptIumContextManagerGetContext(a1, &v19);
    v11 = Context;
    if ( Context >= 0 )
    {
      phAlgorithm = 0;
      *a2 = 0;
      Context = BCryptOpenAlgorithmProvider(&phAlgorithm, a3, 0, dwFlags);
      v11 = Context;
      if ( Context >= 0 )
      {
        BCryptIsoObject = (struct _BCRYPT_ISO_OBJECT *)AllocateBCryptIsoObject(phAlgorithm, 1112100673);
        v15 = BCryptIsoObject;
        if ( BCryptIsoObject )
        {
          v16 = IndexBCryptIsoObject(v19, BCryptIsoObject);
          v11 = v16;
          if ( v16 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                109,
                &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
                (unsigned int)v16);
            BCryptIumDereferenceObject(v15);
          }
          else
          {
            *a2 = *((_QWORD *)v15 + 3);
          }
        }
        else
        {
          v11 = -1073741801;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              108,
              &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
              3221225495LL);
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
        }
        goto LABEL_30;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v13 = 110;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v11;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_31;
      v13 = 107;
    }
    WPP_SF_d(v10[2], v13, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, (unsigned int)Context);
LABEL_30:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v11 = -1073741637;
  if ( v10 == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)v10 + 28) & 1) != 0 )
  {
    WPP_SF_Sd((unsigned int)v10[2], 106, v9, (_DWORD)a3, 187);
    goto LABEL_30;
  }
LABEL_31:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
    WPP_SF_d(v10[2], 111, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x140010cd0  push    rbx
0x140010cd2  push    rbp
0x140010cd3  push    rsi
0x140010cd4  push    rdi
0x140010cd5  push    r12
0x140010cd7  push    r15
0x140010cd9  sub     rsp, 48h
0x140010cdd  mov     rdi, r8
0x140010ce0  mov     rsi, rdx
0x140010ce3  mov     rbx, rcx
0x140010ce6  mov     r11, cs:WPP_GLOBAL_Control
0x140010ced  lea     r15, WPP_GLOBAL_Control
0x140010cf4  mov     ebp, [rsp+78h+dwFlags]
0x140010cfb  cmp     r11, r15
0x140010cfe  jz      short loc_140010D2C
0x140010d00  test    byte ptr [r11+1Ch], 4
0x140010d05  jz      short loc_140010D2C
0x140010d07  mov     rcx, [r11+10h]
0x140010d0b  lea     rax, aNull_0; "(null)"
0x140010d12  test    r8, r8
0x140010d15  mov     [rsp+78h+var_58], ebp
0x140010d19  mov     r9, r8
0x140010d1c  cmovz   r9, rax
0x140010d20  call    WPP_SF_SD
0x140010d25  mov     r11, cs:WPP_GLOBAL_Control
0x140010d2c  mov     rcx, rdi; unsigned __int16 *
0x140010d2f  call    ?IsKeyGuardSupportedAlgorithmName@@YAHPEBG@Z; IsKeyGuardSupportedAlgorithmName(ushort const *)
0x140010d34  lea     r12, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140010d3b  test    eax, eax
0x140010d3d  jnz     short loc_140010D70
0x140010d3f  mov     ebx, 0C00000BBh
0x140010d44  cmp     r11, r15
0x140010d47  jz      loc_140010EC8
0x140010d4d  test    byte ptr [r11+1Ch], 1
0x140010d52  jz      loc_140010EA8
0x140010d58  mov     rcx, [r11+10h]
0x140010d5c  lea     edx, [rax+6Ah]
0x140010d5f  mov     r9, rdi
0x140010d62  mov     [rsp+78h+var_58], ebx
0x140010d66  call    WPP_SF_Sd
0x140010d6b  jmp     loc_140010EA1
0x140010d70  lea     rdx, [rsp+78h+var_40]
0x140010d75  mov     [rsp+78h+var_40], 0
0x140010d7e  mov     rcx, rbx
0x140010d81  call    BCryptIumContextManagerGetContext
0x140010d86  mov     ebx, eax
0x140010d88  test    eax, eax
0x140010d8a  jns     short loc_140010DB1
0x140010d8c  mov     r11, cs:WPP_GLOBAL_Control
0x140010d93  cmp     r11, r15
0x140010d96  jz      loc_140010EC8
0x140010d9c  test    byte ptr [r11+1Ch], 4
0x140010da1  jz      loc_140010EA8
0x140010da7  mov     edx, 6Bh ; 'k'
0x140010dac  jmp     loc_140010E92
0x140010db1  mov     r9d, ebp; dwFlags
0x140010db4  mov     [rsp+78h+phAlgorithm], 0
0x140010dbd  xor     r8d, r8d; pszImplementation
0x140010dc0  mov     qword ptr [rsi], 0
0x140010dc7  mov     rdx, rdi; pszAlgId
0x140010dca  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x140010dcf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140010dd5  mov     ebx, eax
0x140010dd7  test    eax, eax
0x140010dd9  js      loc_140010E7A
0x140010ddf  mov     rcx, [rsp+78h+phAlgorithm]
0x140010de4  mov     edx, 42494F41h
0x140010de9  call    AllocateBCryptIsoObject
0x140010dee  mov     rdi, rax
0x140010df1  test    rax, rax
0x140010df4  jnz     short loc_140010E2E
0x140010df6  mov     ebx, 0C0000017h
0x140010dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e02  cmp     rcx, r15
0x140010e05  jz      short loc_140010E1F
0x140010e07  test    byte ptr [rcx+1Ch], 1
0x140010e0b  jz      short loc_140010E1F
0x140010e0d  mov     rcx, [rcx+10h]
0x140010e11  lea     edx, [rax+6Ch]
0x140010e14  mov     r9d, ebx
0x140010e17  mov     r8, r12
0x140010e1a  call    WPP_SF_d
0x140010e1f  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x140010e24  xor     edx, edx; dwFlags
0x140010e26  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140010e2c  jmp     short loc_140010EA1
0x140010e2e  mov     rcx, [rsp+78h+var_40]; struct BCRYPTIUM_CONTEXT *
0x140010e33  mov     rdx, rdi; struct _BCRYPT_ISO_OBJECT *
0x140010e36  call    ?IndexBCryptIsoObject@@YAJPEAUBCRYPTIUM_CONTEXT@@PEAU_BCRYPT_ISO_OBJECT@@@Z; IndexBCryptIsoObject(BCRYPTIUM_CONTEXT *,_BCRYPT_ISO_OBJECT *)
0x140010e3b  mov     ebx, eax
0x140010e3d  test    eax, eax
0x140010e3f  js      short loc_140010E4A
0x140010e41  mov     rax, [rdi+18h]
0x140010e45  mov     [rsi], rax
0x140010e48  jmp     short loc_140010EA1
0x140010e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e51  cmp     rcx, r15
0x140010e54  jz      short loc_140010E70
0x140010e56  test    byte ptr [rcx+1Ch], 1
0x140010e5a  jz      short loc_140010E70
0x140010e5c  mov     rcx, [rcx+10h]
0x140010e60  mov     edx, 6Dh ; 'm'
0x140010e65  mov     r9d, eax
0x140010e68  mov     r8, r12
0x140010e6b  call    WPP_SF_d
0x140010e70  mov     rcx, rdi; hMem
0x140010e73  call    ?BCryptIumDereferenceObject@@YAXPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumDereferenceObject(_BCRYPT_ISO_OBJECT *)
0x140010e78  jmp     short loc_140010EA1
0x140010e7a  mov     r11, cs:WPP_GLOBAL_Control
0x140010e81  cmp     r11, r15
0x140010e84  jz      short loc_140010EC8
0x140010e86  test    byte ptr [r11+1Ch], 1
0x140010e8b  jz      short loc_140010EA8
0x140010e8d  mov     edx, 6Eh ; 'n'
0x140010e92  mov     rcx, [r11+10h]
0x140010e96  mov     r9d, eax
0x140010e99  mov     r8, r12
0x140010e9c  call    WPP_SF_d
0x140010ea1  mov     r11, cs:WPP_GLOBAL_Control
0x140010ea8  cmp     r11, r15
0x140010eab  jz      short loc_140010EC8
0x140010ead  test    byte ptr [r11+1Ch], 4
0x140010eb2  jz      short loc_140010EC8
0x140010eb4  mov     rcx, [r11+10h]
0x140010eb8  mov     edx, 6Fh ; 'o'
0x140010ebd  mov     r9d, ebx
0x140010ec0  mov     r8, r12
0x140010ec3  call    WPP_SF_d
0x140010ec8  mov     eax, ebx
0x140010eca  add     rsp, 48h
0x140010ece  pop     r15
0x140010ed0  pop     r12
0x140010ed2  pop     rdi
0x140010ed3  pop     rsi
0x140010ed4  pop     rbp
0x140010ed5  pop     rbx
0x140010ed6  retn
```
