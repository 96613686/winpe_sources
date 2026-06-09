# WwanProfileGenerateXml

- ea: `0x18000dea0`
- end: `0x18000e03c`
- name: `WwanProfileGenerateXml`
- size: `412`
- prototype: `__int64 __fastcall(OLECHAR *, int, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009b30`
- `0x18000dea0`
- `0x1800125a4`
- `0x180012fe0`
- `0x180013458`
- `0x1800134f8`
- `0x180014010`

## string_xrefs

- `0x18000decf`: `xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://www.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MBNProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.microsoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN/pro`

## pseudocode

```c
__int64 __fastcall WwanProfileGenerateXml(OLECHAR *a1, int a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  struct IXMLDOMDocument2 *v7; // rbx
  unsigned int Profile; // edi
  __int16 *v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rcx
  _WORD *v12; // r14
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  __int16 *v15; // r8
  _WORD *v16; // rdx
  __int16 v17; // r9
  _WORD *v18; // rcx
  void *lpMem; // [rsp+20h] [rbp-48h] BYREF
  struct IXMLDOMDocument2 *v20; // [rsp+70h] [rbp+8h] BYREF

  v20 = 0;
  lpMem = 0;
  *((_DWORD *)a1 + 981) = a2;
  v5 = XcCreateXmlDoc(
         (OLECHAR *)L"xmlns:MBNProfile='http://www.microsoft.com/networking/WWAN/profile/v1' xmlns:MBNProfileV2='http://ww"
                     "w.microsoft.com/networking/WWAN/profile/v2' xmlns:MBNProfileV3='http://www.microsoft.com/networking"
                     "/WWAN/profile/v3' xmlns:MBNProfileV4='http://www.microsoft.com/networking/WWAN/profile/v4' xmlns:MB"
                     "NProfileV5='http://www.microsoft.com/networking/WWAN/profile/v5' xmlns:MBNProfileV6='http://www.mic"
                     "rosoft.com/networking/WWAN/profile/v6' xmlns:MBNProfileV7='http://www.microsoft.com/networking/WWAN"
                     "/profile/v7' xmlns:MBNProfileV8='http://www.microsoft.com/networking/WWAN/profile/v8' xmlns:MBNProf"
                     "ileV9='http://www.microsoft.com/networking/WWAN/profile/v9' ",
         0,
         &v20);
  if ( v5 )
  {
    if ( v20 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v20->lpVtbl->Release)(v20);
    return v5;
  }
  v7 = v20;
  Profile = generateProfile(v20, a1);
  if ( Profile )
  {
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    return Profile;
  }
  Profile = XcGetNodeXmlIndented((struct IXMLDOMNode *)v7, (unsigned __int16 **)&lpMem);
  if ( Profile )
  {
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    return Profile;
  }
  v9 = (__int16 *)lpMem;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)lpMem + v11) );
  v12 = WwanMemAlloc(2 * v11 + 2);
  if ( v12 )
  {
    do
      ++v10;
    while ( v9[v10] );
    v13 = v10 + 1;
    if ( v10 != -1 )
    {
      if ( v13 <= 0x7FFFFFFF )
      {
        v14 = 2147483646;
        v15 = v9;
        v16 = v12;
        do
        {
          if ( !v14 )
            break;
          v17 = *v15;
          if ( !*v15 )
            break;
          ++v15;
          *v16++ = v17;
          --v14;
          --v13;
        }
        while ( v13 );
        v18 = v16 - 1;
        if ( v13 )
          v18 = v16;
        *v18 = 0;
      }
      else
      {
        *v12 = 0;
      }
    }
    Xc_Process_user_free(v9);
    *a3 = v12;
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    return 0;
  }
  else
  {
    Xc_Process_user_free(v9);
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    return 8;
  }
}

```

## disassembly

```asm
0x18000dea0  push    rbx
0x18000dea2  push    rbp
0x18000dea3  push    rsi
0x18000dea4  push    rdi
0x18000dea5  push    r14
0x18000dea7  push    r15
0x18000dea9  sub     rsp, 38h
0x18000dead  mov     esi, r9d
0x18000deb0  mov     r15, r8
0x18000deb3  mov     rdi, rcx
0x18000deb6  xor     ebp, ebp
0x18000deb8  mov     [rsp+68h+arg_0], rbp
0x18000debd  mov     [rsp+68h+lpMem], rbp
0x18000dec2  mov     [rcx+0F54h], edx
0x18000dec8  lea     r8, [rsp+68h+arg_0]; struct IXMLDOMDocument2 **
0x18000decd  xor     edx, edx; struct IXMLDOMSchemaCollection *
0x18000decf  lea     rcx, aXmlnsMbnprofil; "xmlns:MBNProfile='http://www.microsoft."...
0x18000ded6  call    ?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z; XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)
0x18000dedb  mov     ebx, eax
0x18000dedd  test    eax, eax
0x18000dedf  jz      short loc_18000DEFF
0x18000dee1  mov     rcx, [rsp+68h+arg_0]
0x18000dee6  test    rcx, rcx
0x18000dee9  jz      short loc_18000DEF8
0x18000deeb  mov     rdx, [rcx]
0x18000deee  mov     rax, [rdx+10h]
0x18000def2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def7  nop
0x18000def8  mov     eax, ebx
0x18000defa  jmp     loc_18000E02F
0x18000deff  mov     r9d, esi
0x18000df02  xor     r8d, r8d
0x18000df05  mov     rdx, rdi; OLECHAR *
0x18000df08  mov     rbx, [rsp+68h+arg_0]
0x18000df0d  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000df10  call    _generateProfile
0x18000df15  mov     edi, eax
0x18000df17  test    eax, eax
0x18000df19  jz      short loc_18000DF37
0x18000df1b  test    rbx, rbx
0x18000df1e  jz      short loc_18000DF30
0x18000df20  mov     rcx, [rbx]
0x18000df23  mov     rax, [rcx+10h]
0x18000df27  mov     rcx, rbx
0x18000df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2f  nop
0x18000df30  mov     eax, edi
0x18000df32  jmp     loc_18000E02F
0x18000df37  lea     rdx, [rsp+68h+lpMem]; unsigned __int16 **
0x18000df3c  mov     rcx, rbx; struct IXMLDOMNode *
0x18000df3f  call    ?XcGetNodeXmlIndented@@YAKPEAUIXMLDOMNode@@PEAPEAG@Z; XcGetNodeXmlIndented(IXMLDOMNode *,ushort * *)
0x18000df44  mov     edi, eax
0x18000df46  test    eax, eax
0x18000df48  jz      short loc_18000DF61
0x18000df4a  test    rbx, rbx
0x18000df4d  jz      short loc_18000DF5F
0x18000df4f  mov     rcx, [rbx]
0x18000df52  mov     rax, [rcx+10h]
0x18000df56  mov     rcx, rbx
0x18000df59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df5e  nop
0x18000df5f  jmp     short loc_18000DF30
0x18000df61  mov     rsi, [rsp+68h+lpMem]
0x18000df66  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000df6a  mov     rcx, rdi
0x18000df6d  inc     rcx
0x18000df70  cmp     [rsi+rcx*2], bp
0x18000df74  jnz     short loc_18000DF6D
0x18000df76  lea     rcx, ds:2[rcx*2]; Size
0x18000df7e  call    WwanMemAlloc
0x18000df83  mov     r14, rax
0x18000df86  test    rax, rax
0x18000df89  jnz     short loc_18000DFB0
0x18000df8b  mov     rcx, rsi; lpMem
0x18000df8e  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000df93  nop
0x18000df94  test    rbx, rbx
0x18000df97  jz      short loc_18000DFA9
0x18000df99  mov     rax, [rbx]
0x18000df9c  mov     rcx, rbx
0x18000df9f  mov     rax, [rax+10h]
0x18000dfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa8  nop
0x18000dfa9  mov     eax, 8
0x18000dfae  jmp     short loc_18000E02F
0x18000dfb0  inc     rdi
0x18000dfb3  cmp     [rsi+rdi*2], bp
0x18000dfb7  jnz     short loc_18000DFB0
0x18000dfb9  lea     rax, [rdi+1]
0x18000dfbd  test    rax, rax
0x18000dfc0  jz      short loc_18000E00D
0x18000dfc2  cmp     rax, 7FFFFFFFh
0x18000dfc8  jbe     short loc_18000DFD0
0x18000dfca  mov     [r14], bp
0x18000dfce  jmp     short loc_18000E00D
0x18000dfd0  mov     ecx, 7FFFFFFEh
0x18000dfd5  mov     r8, rsi
0x18000dfd8  mov     rdx, r14
0x18000dfdb  test    rcx, rcx
0x18000dfde  jz      short loc_18000DFFF
0x18000dfe0  movzx   r9d, word ptr [r8]
0x18000dfe4  test    r9w, r9w
0x18000dfe8  jz      short loc_18000DFFF
0x18000dfea  add     r8, 2
0x18000dfee  mov     [rdx], r9w
0x18000dff2  add     rdx, 2
0x18000dff6  dec     rcx
0x18000dff9  sub     rax, 1
0x18000dffd  jnz     short loc_18000DFDB
0x18000dfff  lea     rcx, [rdx-2]
0x18000e003  test    rax, rax
0x18000e006  cmovnz  rcx, rdx
0x18000e00a  mov     [rcx], bp
0x18000e00d  mov     rcx, rsi; lpMem
0x18000e010  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000e015  mov     [r15], r14
0x18000e018  test    rbx, rbx
0x18000e01b  jz      short loc_18000E02D
0x18000e01d  mov     rax, [rbx]
0x18000e020  mov     rcx, rbx
0x18000e023  mov     rax, [rax+10h]
0x18000e027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e02c  nop
0x18000e02d  xor     eax, eax
0x18000e02f  add     rsp, 38h
0x18000e033  pop     r15
0x18000e035  pop     r14
0x18000e037  pop     rdi
0x18000e038  pop     rsi
0x18000e039  pop     rbp
0x18000e03a  pop     rbx
0x18000e03b  retn
```
