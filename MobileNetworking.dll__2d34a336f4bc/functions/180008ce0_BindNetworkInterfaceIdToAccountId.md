# BindNetworkInterfaceIdToAccountId

- ea: `0x180008ce0`
- end: `0x180008fe0`
- name: `BindNetworkInterfaceIdToAccountId`
- size: `768`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005910`
- `0x180006000`
- `0x180006340`
- `0x180008cb0`
- `0x180008ce0`
- `0x180008ff0`
- `0x180009020`
- `0x180009850`
- `0x18000b6f4`
- `0x18000d978`

## string_xrefs

- `0x180008ef4`: `BindingToken`

## pseudocode

```c
__int64 __fastcall BindNetworkInterfaceIdToAccountId(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  PVOID *v6; // rcx
  unsigned __int64 v7; // rdx
  signed int BindingRegistryPath; // ebp
  HKEY v9; // rdx
  unsigned __int16 *v10; // r9
  int v11; // eax
  HKEY v12; // rdx
  unsigned __int16 *v13; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // r9d
  int v18; // eax
  unsigned int v19; // r9d
  int v20; // eax
  unsigned __int64 v21; // r8
  unsigned int v22; // r9d
  int v23; // eax
  unsigned int v25; // [rsp+20h] [rbp-538h]
  unsigned int v26; // [rsp+20h] [rbp-538h]
  struct _SECURITY_ATTRIBUTES *v27; // [rsp+30h] [rbp-528h]
  struct _SECURITY_ATTRIBUTES *v28; // [rsp+30h] [rbp-528h]
  unsigned int *v29; // [rsp+38h] [rbp-520h]
  unsigned int *v30; // [rsp+38h] [rbp-520h]
  _QWORD v31[3]; // [rsp+40h] [rbp-518h] BYREF
  _QWORD v32[3]; // [rsp+58h] [rbp-500h] BYREF
  unsigned __int16 v33[72]; // [rsp+70h] [rbp-4E8h] BYREF
  unsigned __int16 v34[264]; // [rsp+100h] [rbp-458h] BYREF
  unsigned __int16 v35[264]; // [rsp+310h] [rbp-248h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset(v31, 0, sizeof(v31));
  memset(v32, 0, sizeof(v32));
  if ( a2 && a1 )
  {
    BindingRegistryPath = GetBindingRegistryPath(a2, (unsigned __int64)a2, v34);
    if ( BindingRegistryPath < 0 )
      goto LABEL_45;
    BindingRegistryPath = GetAccountRegistryPath(a1, v7, v35);
    if ( BindingRegistryPath < 0 )
      goto LABEL_45;
    v11 = ATL::CRegKey::Create((ATL::CRegKey *)v31, v9, v34, v10, v25, 0x20006u, v27, v29);
    BindingRegistryPath = v11;
    if ( !v11 )
      goto LABEL_15;
    if ( v11 > 0 )
      BindingRegistryPath = (unsigned __int16)v11 | 0x80070000;
    if ( BindingRegistryPath < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_45;
      v15 = 12;
    }
    else
    {
LABEL_15:
      v16 = ATL::CRegKey::Create((ATL::CRegKey *)v32, v12, v35, v13, v26, 0x20006u, v28, v30);
      BindingRegistryPath = v16;
      if ( !v16 )
        goto LABEL_22;
      if ( v16 > 0 )
        BindingRegistryPath = (unsigned __int16)v16 | 0x80070000;
      if ( BindingRegistryPath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_45;
        v15 = 13;
      }
      else
      {
LABEL_22:
        v18 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v32, L"CurrentNetworkInterface", a2, v17);
        BindingRegistryPath = v18;
        if ( !v18 )
          goto LABEL_29;
        if ( v18 > 0 )
          BindingRegistryPath = (unsigned __int16)v18 | 0x80070000;
        if ( BindingRegistryPath < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_45;
          v15 = 14;
        }
        else
        {
LABEL_29:
          v20 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v31, L"NetworkAccountId", a1, v19);
          BindingRegistryPath = v20;
          if ( !v20 )
            goto LABEL_36;
          if ( v20 > 0 )
            BindingRegistryPath = (unsigned __int16)v20 | 0x80070000;
          if ( BindingRegistryPath < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_45;
            v15 = 15;
          }
          else
          {
LABEL_36:
            BindingRegistryPath = CalculateBindingToken(a1, a3, v21, v33);
            if ( BindingRegistryPath < 0
              || (v23 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v31, L"BindingToken", v33, v22)) == 0
              || (v23 > 0 ? (BindingRegistryPath = (unsigned __int16)v23 | 0x80070000) : (BindingRegistryPath = v23),
                  (v14 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == &WPP_GLOBAL_Control)
               || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0) )
            {
LABEL_45:
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              ATL::CRegKey::Close((ATL::CRegKey *)v31);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  WPP_18307326125a33c7b51732b3213c2b2b_Traceguids,
                  (unsigned int)BindingRegistryPath);
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              ATL::CRegKey::Close((ATL::CRegKey *)v31);
              return (unsigned int)BindingRegistryPath;
            }
            v15 = 16;
          }
        }
      }
    }
    WPP_SF_d(v14[2], v15, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids, (unsigned int)BindingRegistryPath);
    goto LABEL_45;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    WPP_SF_(v6[2], 11, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008ce0  push    rbx
0x180008ce2  push    rbp
0x180008ce3  push    rsi
0x180008ce4  push    rdi
0x180008ce5  push    r14
0x180008ce7  sub     rsp, 530h
0x180008cee  mov     rax, cs:__security_cookie
0x180008cf5  xor     rax, rsp
0x180008cf8  mov     [rsp+558h+var_38], rax
0x180008d00  mov     rsi, r8
0x180008d03  mov     rbx, rdx
0x180008d06  mov     rdi, rcx
0x180008d09  lea     r14, WPP_GLOBAL_Control
0x180008d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d17  cmp     rcx, r14
0x180008d1a  jz      short loc_180008D3E
0x180008d1c  test    byte ptr [rcx+1Ch], 10h
0x180008d20  jz      short loc_180008D3E
0x180008d22  mov     edx, 0Ah
0x180008d27  lea     r8, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids
0x180008d2e  mov     rcx, [rcx+10h]
0x180008d32  call    WPP_SF_
0x180008d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d3e  xor     eax, eax
0x180008d40  mov     [rsp+558h+var_518], rax
0x180008d45  mov     [rsp+558h+var_510], rax
0x180008d4a  mov     [rsp+558h+var_508], rax
0x180008d4f  mov     [rsp+558h+var_500], rax
0x180008d54  mov     [rsp+558h+var_4F8], rax
0x180008d59  mov     [rsp+558h+var_4F0], rax
0x180008d5e  test    rbx, rbx
0x180008d61  jz      loc_180008F9C
0x180008d67  test    rdi, rdi
0x180008d6a  jz      loc_180008F9C
0x180008d70  lea     r8, [rsp+558h+var_458]; unsigned __int16 *
0x180008d78  mov     rcx, rbx; unsigned __int16 *
0x180008d7b  call    ?GetBindingRegistryPath@@YAJPEBG_KPEAG@Z; GetBindingRegistryPath(ushort const *,unsigned __int64,ushort *)
0x180008d80  mov     ebp, eax
0x180008d82  test    eax, eax
0x180008d84  js      loc_180008F46
0x180008d8a  lea     r8, [rsp+558h+var_248]; unsigned __int16 *
0x180008d92  mov     rcx, rdi; unsigned __int16 *
0x180008d95  call    ?GetAccountRegistryPath@@YAJPEBG_KPEAG@Z; GetAccountRegistryPath(ushort const *,unsigned __int64,ushort *)
0x180008d9a  mov     ebp, eax
0x180008d9c  test    eax, eax
0x180008d9e  js      loc_180008F46
0x180008da4  mov     [rsp+558h+var_530], 20006h; unsigned int
0x180008dac  lea     r8, [rsp+558h+var_458]; unsigned __int16 *
0x180008db4  lea     rcx, [rsp+558h+var_518]; this
0x180008db9  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180008dbe  mov     ebp, eax
0x180008dc0  test    eax, eax
0x180008dc2  jz      short loc_180008DF7
0x180008dc4  jle     short loc_180008DCF
0x180008dc6  movzx   ebp, ax
0x180008dc9  or      ebp, 80070000h
0x180008dcf  test    ebp, ebp
0x180008dd1  jns     short loc_180008DF7
0x180008dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dda  cmp     rcx, r14
0x180008ddd  jz      loc_180008F46
0x180008de3  test    byte ptr [rcx+1Ch], 2
0x180008de7  jz      loc_180008F46
0x180008ded  mov     edx, 0Ch
0x180008df2  jmp     loc_180008F33
0x180008df7  mov     [rsp+558h+var_530], 20006h; unsigned int
0x180008dff  lea     r8, [rsp+558h+var_248]; unsigned __int16 *
0x180008e07  lea     rcx, [rsp+558h+var_500]; this
0x180008e0c  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180008e11  mov     ebp, eax
0x180008e13  test    eax, eax
0x180008e15  jz      short loc_180008E4A
0x180008e17  jle     short loc_180008E22
0x180008e19  movzx   ebp, ax
0x180008e1c  or      ebp, 80070000h
0x180008e22  test    ebp, ebp
0x180008e24  jns     short loc_180008E4A
0x180008e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e2d  cmp     rcx, r14
0x180008e30  jz      loc_180008F46
0x180008e36  test    byte ptr [rcx+1Ch], 2
0x180008e3a  jz      loc_180008F46
0x180008e40  mov     edx, 0Dh
0x180008e45  jmp     loc_180008F33
0x180008e4a  mov     r8, rbx; unsigned __int16 *
0x180008e4d  lea     rdx, Value; "CurrentNetworkInterface"
0x180008e54  lea     rcx, [rsp+558h+var_500]; this
0x180008e59  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180008e5e  mov     ebp, eax
0x180008e60  test    eax, eax
0x180008e62  jz      short loc_180008E97
0x180008e64  jle     short loc_180008E6F
0x180008e66  movzx   ebp, ax
0x180008e69  or      ebp, 80070000h
0x180008e6f  test    ebp, ebp
0x180008e71  jns     short loc_180008E97
0x180008e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e7a  cmp     rcx, r14
0x180008e7d  jz      loc_180008F46
0x180008e83  test    byte ptr [rcx+1Ch], 2
0x180008e87  jz      loc_180008F46
0x180008e8d  mov     edx, 0Eh
0x180008e92  jmp     loc_180008F33
0x180008e97  mov     r8, rdi; unsigned __int16 *
0x180008e9a  lea     rdx, ValueName; "NetworkAccountId"
0x180008ea1  lea     rcx, [rsp+558h+var_518]; this
0x180008ea6  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180008eab  mov     ebp, eax
0x180008ead  test    eax, eax
0x180008eaf  jz      short loc_180008ED9
0x180008eb1  jle     short loc_180008EBC
0x180008eb3  movzx   ebp, ax
0x180008eb6  or      ebp, 80070000h
0x180008ebc  test    ebp, ebp
0x180008ebe  jns     short loc_180008ED9
0x180008ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ec7  cmp     rcx, r14
0x180008eca  jz      short loc_180008F46
0x180008ecc  test    byte ptr [rcx+1Ch], 2
0x180008ed0  jz      short loc_180008F46
0x180008ed2  mov     edx, 0Fh
0x180008ed7  jmp     short loc_180008F33
0x180008ed9  lea     r9, [rsp+558h+var_4E8]; unsigned __int16 *
0x180008ede  mov     rdx, rsi; unsigned __int16 *
0x180008ee1  mov     rcx, rdi; unsigned __int16 *
0x180008ee4  call    ?CalculateBindingToken@@YAJPEBG0_KPEAG@Z; CalculateBindingToken(ushort const *,ushort const *,unsigned __int64,ushort *)
0x180008ee9  mov     ebp, eax
0x180008eeb  test    eax, eax
0x180008eed  js      short loc_180008F46
0x180008eef  lea     r8, [rsp+558h+var_4E8]; unsigned __int16 *
0x180008ef4  lea     rdx, aBindingtoken; "BindingToken"
0x180008efb  lea     rcx, [rsp+558h+var_518]; this
0x180008f00  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180008f05  test    eax, eax
0x180008f07  jz      short loc_180008F46
0x180008f09  jg      short loc_180008F0F
0x180008f0b  mov     ebp, eax
0x180008f0d  jmp     short loc_180008F18
0x180008f0f  movzx   ebp, ax
0x180008f12  or      ebp, 80070000h
0x180008f18  test    ebp, ebp
0x180008f1a  jns     short loc_180008F46
0x180008f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f23  cmp     rcx, r14
0x180008f26  jz      short loc_180008F46
0x180008f28  test    byte ptr [rcx+1Ch], 2
0x180008f2c  jz      short loc_180008F46
0x180008f2e  mov     edx, 10h
0x180008f33  mov     r9d, ebp
0x180008f36  lea     r8, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids
0x180008f3d  mov     rcx, [rcx+10h]
0x180008f41  call    WPP_SF_d
0x180008f46  lea     rcx, [rsp+558h+var_500]; this
0x180008f4b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008f50  lea     rcx, [rsp+558h+var_518]; this
0x180008f55  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f61  cmp     rcx, r14
0x180008f64  jz      short loc_180008F84
0x180008f66  test    byte ptr [rcx+1Ch], 10h
0x180008f6a  jz      short loc_180008F84
0x180008f6c  mov     edx, 11h
0x180008f71  mov     r9d, ebp
0x180008f74  lea     r8, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids
0x180008f7b  mov     rcx, [rcx+10h]
0x180008f7f  call    WPP_SF_d
0x180008f84  lea     rcx, [rsp+558h+var_500]; this
0x180008f89  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008f8e  lea     rcx, [rsp+558h+var_518]; this
0x180008f93  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008f98  mov     eax, ebp
0x180008f9a  jmp     short loc_180008FC2
0x180008f9c  cmp     rcx, r14
0x180008f9f  jz      short loc_180008FBD
0x180008fa1  test    byte ptr [rcx+1Ch], 2
0x180008fa5  jz      short loc_180008FBD
0x180008fa7  mov     edx, 0Bh
0x180008fac  lea     r8, WPP_18307326125a33c7b51732b3213c2b2b_Traceguids
0x180008fb3  mov     rcx, [rcx+10h]
0x180008fb7  call    WPP_SF_
0x180008fbc  nop
0x180008fbd  mov     eax, 80070057h
0x180008fc2  mov     rcx, [rsp+558h+var_38]
0x180008fca  xor     rcx, rsp; StackCookie
0x180008fcd  call    __security_check_cookie
0x180008fd2  add     rsp, 530h
0x180008fd9  pop     r14
0x180008fdb  pop     rdi
0x180008fdc  pop     rsi
0x180008fdd  pop     rbp
0x180008fde  pop     rbx
0x180008fdf  retn
```
