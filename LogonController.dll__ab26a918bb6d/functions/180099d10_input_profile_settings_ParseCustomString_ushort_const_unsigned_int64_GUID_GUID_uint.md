# input_profile_settings::ParseCustomString(ushort const *,unsigned __int64 *,_GUID *,_GUID *,uint *)

- ea: `0x180099d10`
- end: `0x180099fbc`
- name: `?ParseCustomString@input_profile_settings@@YAJPEBGPEA_KPEAU_GUID@@2PEAI@Z`
- size: `684`
- prototype: `int(input_profile_settings *__hidden this, const unsigned __int16 *, unsigned __int64 *, struct _GUID *, struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009793c`
- `0x180097b18`

## callees

- `0x18003a57c`
- `0x180096208`
- `0x180099b44`
- `0x180099d10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099dc9`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x180099dfc`
- `Bcp47Langs!CompactTagFromBcp47Internal` at `0x180099dfc`

## pseudocode

```c
__int64 __fastcall input_profile_settings::ParseCustomString(
        input_profile_settings *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        struct _GUID *a5)
{
  struct _GUID *v9; // r15
  unsigned int v10; // ebx
  __int64 v11; // rdi
  HRESULT v12; // eax
  int v13; // edx
  int v14; // ecx
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rdi
  input_profile_settings *v17; // rcx
  int v18; // r9d
  unsigned int v20[22]; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+90h] [rbp+8h] BYREF

  if ( !this )
  {
    v10 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      return v10;
    v18 = 388;
    goto LABEL_44;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      return v10;
    v18 = 389;
    goto LABEL_44;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      return v10;
    v18 = 390;
    goto LABEL_44;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      return v10;
    v18 = 391;
    goto LABEL_44;
  }
  v9 = a5;
  if ( !a5 )
  {
    v10 = -2147024809;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      return v10;
    v18 = 392;
    goto LABEL_44;
  }
  *(_QWORD *)a2 = 0;
  v10 = 0;
  v9->Data1 = 0;
  LODWORD(v11) = 0;
  *a3 = GUID_NULL;
  *a4 = GUID_NULL;
  if ( *(_WORD *)this != 123 )
  {
    if ( !*(_WORD *)this )
      goto LABEL_28;
    do
    {
      if ( *((_WORD *)this + (unsigned int)v11) == 58 )
        break;
      v11 = (unsigned int)(v11 + 1);
    }
    while ( *((_WORD *)this + v11) );
    if ( !(_DWORD)v11 )
    {
LABEL_28:
      v10 = -2147024809;
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
        return v10;
      v18 = 408;
      goto LABEL_44;
    }
    string = 0;
    v12 = WindowsCreateString((PCNZWCH)this, v11, &string);
    v10 = v12;
    if ( v12 < 0 )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(
          v14,
          v13,
          (unsigned int)"input_profile_settings::ParseCustomString",
          411,
          v12);
      return v10;
    }
    v10 = CompactTagFromBcp47Internal(string, a2);
    WindowsDeleteString(string);
    if ( !*(_QWORD *)a2 )
    {
      v10 = -2147024809;
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
        return v10;
      v18 = 414;
      goto LABEL_44;
    }
    if ( *((_WORD *)this + (unsigned int)v11) == 58 )
      LODWORD(v11) = v11 + 1;
  }
  v15 = (const unsigned __int16 *)((char *)this + 2 * (unsigned int)v11);
  if ( *v15 == 123 )
  {
    if ( StringToCLSIDNonNullTerminate(v15, a3) )
    {
      v16 = (unsigned int)(v11 + 38);
      if ( StringToCLSIDNonNullTerminate((const unsigned __int16 *)this + v16, a4) )
      {
        v11 = (unsigned int)(v16 + 38);
        if ( *((_WORD *)this + v11) == 58 )
          LODWORD(v11) = v11 + 1;
        goto LABEL_22;
      }
      v10 = -2147024809;
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
        return v10;
      v18 = 429;
    }
    else
    {
      v10 = -2147024809;
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
        return v10;
      v18 = 427;
    }
LABEL_44:
    McTemplateU0sqq_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"input_profile_settings::ParseCustomString",
      v18,
      87);
    return v10;
  }
LABEL_22:
  v17 = (input_profile_settings *)((char *)this + 2 * (unsigned int)v11);
  if ( *(_WORD *)v17 )
  {
    LODWORD(string) = 0;
    v20[0] = 0;
    if ( input_profile_settings::HexStringToUint(v17, (const unsigned __int16 *)&string, v20, &a4->Data1)
      && (_DWORD)string == 8 )
    {
      v9->Data1 = v20[0];
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180099d10  push    rbx
0x180099d12  push    rbp
0x180099d13  push    rsi
0x180099d14  push    rdi
0x180099d15  push    r12
0x180099d17  push    r13
0x180099d19  push    r14
0x180099d1b  push    r15
0x180099d1d  sub     rsp, 48h
0x180099d21  xor     r13d, r13d
0x180099d24  mov     r12, r9
0x180099d27  mov     rbp, r8
0x180099d2a  mov     r14, rdx
0x180099d2d  mov     rsi, rcx
0x180099d30  test    rcx, rcx
0x180099d33  jz      loc_180099F81
0x180099d39  test    rdx, rdx
0x180099d3c  jz      loc_180099F6B
0x180099d42  test    r8, r8
0x180099d45  jz      loc_180099F55
0x180099d4b  test    r9, r9
0x180099d4e  jz      loc_180099F3F
0x180099d54  mov     r15, [rsp+88h+arg_20]
0x180099d5c  test    r15, r15
0x180099d5f  jz      loc_180099F29
0x180099d65  mov     [rdx], r13
0x180099d68  mov     ebx, r13d
0x180099d6b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180099d72  mov     [r15], r13d
0x180099d75  mov     edi, r13d
0x180099d78  movdqu  xmmword ptr [r8], xmm0
0x180099d7d  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180099d84  movdqu  xmmword ptr [r9], xmm1
0x180099d89  cmp     word ptr [rcx], 7Bh ; '{'
0x180099d8d  jz      loc_180099E26
0x180099d93  cmp     [rcx], r13w
0x180099d97  jz      loc_180099ED5
0x180099d9d  mov     eax, edi
0x180099d9f  cmp     word ptr [rcx+rax*2], 3Ah ; ':'
0x180099da4  jz      short loc_180099DAF
0x180099da6  inc     edi
0x180099da8  cmp     [rcx+rdi*2], r13w
0x180099dad  jnz     short loc_180099D9D
0x180099daf  test    edi, edi
0x180099db1  jz      loc_180099ED5
0x180099db7  lea     r8, [rsp+88h+string]; string
0x180099dbf  mov     [rsp+88h+string], r13
0x180099dc7  mov     edx, edi; length
0x180099dc9  call    cs:__imp_WindowsCreateString
0x180099dcf  mov     ebx, eax
0x180099dd1  test    eax, eax
0x180099dd3  jns     short loc_180099DF1
0x180099dd5  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099ddc  jz      loc_180099FA9
0x180099de2  mov     [rsp+88h+var_68], eax
0x180099de6  mov     r9d, 19Bh
0x180099dec  jmp     loc_180099F9D
0x180099df1  mov     rcx, [rsp+88h+string]
0x180099df9  mov     rdx, r14
0x180099dfc  call    cs:__imp_CompactTagFromBcp47Internal
0x180099e02  mov     rcx, [rsp+88h+string]; string
0x180099e0a  mov     ebx, eax
0x180099e0c  call    cs:__imp_WindowsDeleteString
0x180099e12  cmp     [r14], r13
0x180099e15  jz      loc_180099EB8
0x180099e1b  mov     eax, edi
0x180099e1d  cmp     word ptr [rsi+rax*2], 3Ah ; ':'
0x180099e22  jnz     short loc_180099E26
0x180099e24  inc     edi
0x180099e26  mov     eax, edi
0x180099e28  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x180099e2c  cmp     word ptr [rcx], 7Bh ; '{'
0x180099e30  jnz     short loc_180099E67
0x180099e32  mov     rdx, rbp; struct _GUID *
0x180099e35  call    ?StringToCLSIDNonNullTerminate@@YAPEBGPEBGPEAU_GUID@@@Z; StringToCLSIDNonNullTerminate(ushort const *,_GUID *)
0x180099e3a  test    rax, rax
0x180099e3d  jz      loc_180099F0F
0x180099e43  add     edi, 26h ; '&'
0x180099e46  mov     rdx, r12; struct _GUID *
0x180099e49  lea     rcx, [rsi+rdi*2]; unsigned __int16 *
0x180099e4d  call    ?StringToCLSIDNonNullTerminate@@YAPEBGPEBGPEAU_GUID@@@Z; StringToCLSIDNonNullTerminate(ushort const *,_GUID *)
0x180099e52  test    rax, rax
0x180099e55  jz      loc_180099EF2
0x180099e5b  add     edi, 26h ; '&'
0x180099e5e  cmp     word ptr [rsi+rdi*2], 3Ah ; ':'
0x180099e63  jnz     short loc_180099E67
0x180099e65  inc     edi
0x180099e67  mov     eax, edi
0x180099e69  lea     rcx, [rsi+rax*2]; this
0x180099e6d  cmp     [rcx], r13w
0x180099e71  jz      loc_180099FA9
0x180099e77  lea     r8, [rsp+88h+var_58]; unsigned int *
0x180099e7c  mov     dword ptr [rsp+88h+string], r13d
0x180099e84  lea     rdx, [rsp+88h+string]; unsigned __int16 *
0x180099e8c  mov     [rsp+88h+var_58], r13d
0x180099e91  call    ?HexStringToUint@input_profile_settings@@YA_NPEBGPEAI1@Z; input_profile_settings::HexStringToUint(ushort const *,uint *,uint *)
0x180099e96  test    al, al
0x180099e98  jz      loc_180099FA9
0x180099e9e  cmp     dword ptr [rsp+88h+string], 8
0x180099ea6  jnz     loc_180099FA9
0x180099eac  mov     eax, [rsp+88h+var_58]
0x180099eb0  mov     [r15], eax
0x180099eb3  jmp     loc_180099FA9
0x180099eb8  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099ebf  mov     ebx, 80070057h
0x180099ec4  jz      loc_180099FA9
0x180099eca  mov     r9d, 19Eh
0x180099ed0  jmp     loc_180099F95
0x180099ed5  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099edc  mov     ebx, 80070057h
0x180099ee1  jz      loc_180099FA9
0x180099ee7  mov     r9d, 198h
0x180099eed  jmp     loc_180099F95
0x180099ef2  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099ef9  mov     ebx, 80070057h
0x180099efe  jz      loc_180099FA9
0x180099f04  mov     r9d, 1ADh
0x180099f0a  jmp     loc_180099F95
0x180099f0f  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f16  mov     ebx, 80070057h
0x180099f1b  jz      loc_180099FA9
0x180099f21  mov     r9d, 1ABh
0x180099f27  jmp     short loc_180099F95
0x180099f29  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f30  mov     ebx, 80070057h
0x180099f35  jz      short loc_180099FA9
0x180099f37  mov     r9d, 188h
0x180099f3d  jmp     short loc_180099F95
0x180099f3f  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f46  mov     ebx, 80070057h
0x180099f4b  jz      short loc_180099FA9
0x180099f4d  mov     r9d, 187h
0x180099f53  jmp     short loc_180099F95
0x180099f55  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f5c  mov     ebx, 80070057h
0x180099f61  jz      short loc_180099FA9
0x180099f63  mov     r9d, 186h
0x180099f69  jmp     short loc_180099F95
0x180099f6b  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f72  mov     ebx, 80070057h
0x180099f77  jz      short loc_180099FA9
0x180099f79  mov     r9d, 185h
0x180099f7f  jmp     short loc_180099F95
0x180099f81  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180099f88  mov     ebx, 80070057h
0x180099f8d  jz      short loc_180099FA9
0x180099f8f  mov     r9d, 184h
0x180099f95  mov     [rsp+88h+var_68], 80070057h
0x180099f9d  lea     r8, aInputProfileSe; "input_profile_settings::ParseCustomStri"...
0x180099fa4  call    McTemplateU0sqq_EventWriteTransfer
0x180099fa9  mov     eax, ebx
0x180099fab  add     rsp, 48h
0x180099faf  pop     r15
0x180099fb1  pop     r14
0x180099fb3  pop     r13
0x180099fb5  pop     r12
0x180099fb7  pop     rdi
0x180099fb8  pop     rsi
0x180099fb9  pop     rbp
0x180099fba  pop     rbx
0x180099fbb  retn
```
