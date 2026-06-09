# ProvIumCreateMachineSelfSignedCertificate

- ea: `0x140004b70`
- end: `0x140004ca2`
- name: `ProvIumCreateMachineSelfSignedCertificate`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003af0`
- `0x140003e58`
- `0x140004b70`
- `0x140004ca8`
- `0x140006720`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x140004c77`
- `bcrypt!BCryptDestroyKey` at `0x140004c77`

## string_xrefs

- `0x140004c53`: `ProvIumCreateMachineSelfSignedCertificate`

## pseudocode

```c
__int64 __fastcall ProvIumCreateMachineSelfSignedCertificate(
        __int64 a1,
        unsigned int a2,
        const void *a3,
        __int64 a4,
        _DWORD *a5,
        unsigned __int8 **a6)
{
  int SelfSignedCertificate; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  BCRYPT_KEY_HANDLE hKey; // [rsp+30h] [rbp-38h] BYREF
  void *v12; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  v12 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
    return 3221225485LL;
  *a5 = 0;
  *a6 = 0;
  SelfSignedCertificate = ImportMachineKey(a3, a2, &hKey, &v12);
  if ( SelfSignedCertificate >= 0 )
  {
    SelfSignedCertificate = CreateSelfSignedCertificate(hKey, (__int128 *)v12, a4, a5, a6);
    if ( SelfSignedCertificate >= 0 )
      goto LABEL_15;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 27;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v9 = 26;
  }
  WPP_SF_sd(
    v8[2],
    v9,
    (unsigned int)&WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids,
    (unsigned int)"ProvIumCreateMachineSelfSignedCertificate",
    SelfSignedCertificate);
LABEL_15:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v12 )
    SafeAllocaFreeToHeap(v12);
  return (unsigned int)SelfSignedCertificate;
}

```

## disassembly

```asm
0x140004b70  mov     r11, rsp
0x140004b73  push    rbx
0x140004b74  push    rsi
0x140004b75  push    rdi
0x140004b76  push    r15
0x140004b78  sub     rsp, 48h
0x140004b7c  mov     qword ptr [r11-38h], 0
0x140004b84  mov     r15, r9
0x140004b87  mov     qword ptr [r11-30h], 0
0x140004b8f  mov     rax, r8
0x140004b92  test    edx, edx
0x140004b94  jz      loc_140004C93
0x140004b9a  test    rax, rax
0x140004b9d  jz      loc_140004C93
0x140004ba3  test    r9, r9
0x140004ba6  jz      loc_140004C93
0x140004bac  mov     rdi, [rsp+68h+arg_20]
0x140004bb4  test    rdi, rdi
0x140004bb7  jz      loc_140004C93
0x140004bbd  mov     rsi, [rsp+68h+arg_28]
0x140004bc5  test    rsi, rsi
0x140004bc8  jz      loc_140004C93
0x140004bce  mov     dword ptr [rdi], 0
0x140004bd4  lea     r9, [r11-30h]
0x140004bd8  lea     r8, [r11-38h]
0x140004bdc  mov     qword ptr [rsi], 0
0x140004be3  mov     rcx, rax
0x140004be6  call    ImportMachineKey
0x140004beb  mov     ebx, eax
0x140004bed  test    eax, eax
0x140004bef  jns     short loc_140004C11
0x140004bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bf8  lea     rax, WPP_GLOBAL_Control
0x140004bff  cmp     rcx, rax
0x140004c02  jz      short loc_140004C6A
0x140004c04  test    byte ptr [rcx+1Ch], 1
0x140004c08  jz      short loc_140004C6A
0x140004c0a  mov     edx, 1Ah
0x140004c0f  jmp     short loc_140004C4F
0x140004c11  mov     rdx, [rsp+68h+var_30]
0x140004c16  mov     r9, rdi
0x140004c19  mov     rcx, [rsp+68h+hKey]
0x140004c1e  mov     r8, r15
0x140004c21  mov     [rsp+68h+var_48], rsi
0x140004c26  call    CreateSelfSignedCertificate
0x140004c2b  mov     ebx, eax
0x140004c2d  test    eax, eax
0x140004c2f  jns     short loc_140004C6A
0x140004c31  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c38  lea     rax, WPP_GLOBAL_Control
0x140004c3f  cmp     rcx, rax
0x140004c42  jz      short loc_140004C6A
0x140004c44  test    byte ptr [rcx+1Ch], 1
0x140004c48  jz      short loc_140004C6A
0x140004c4a  mov     edx, 1Bh
0x140004c4f  mov     rcx, [rcx+10h]
0x140004c53  lea     r9, aProviumcreatem_0; "ProvIumCreateMachineSelfSignedCertifica"...
0x140004c5a  lea     r8, WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids
0x140004c61  mov     dword ptr [rsp+68h+var_48], ebx
0x140004c65  call    WPP_SF_sd
0x140004c6a  cmp     [rsp+68h+hKey], 0
0x140004c70  jz      short loc_140004C7D
0x140004c72  mov     rcx, [rsp+68h+hKey]; hKey
0x140004c77  call    cs:__imp_BCryptDestroyKey
0x140004c7d  cmp     [rsp+68h+var_30], 0
0x140004c83  jz      short loc_140004C8F
0x140004c85  mov     rcx, [rsp+68h+var_30]; void *
0x140004c8a  call    SafeAllocaFreeToHeap
0x140004c8f  mov     eax, ebx
0x140004c91  jmp     short loc_140004C98
0x140004c93  mov     eax, 0C000000Dh
0x140004c98  add     rsp, 48h
0x140004c9c  pop     r15
0x140004c9e  pop     rdi
0x140004c9f  pop     rsi
0x140004ca0  pop     rbx
0x140004ca1  retn
```
