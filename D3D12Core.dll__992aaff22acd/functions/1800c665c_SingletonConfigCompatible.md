# SingletonConfigCompatible

- ea: `0x1800c665c`
- end: `0x1800c69c0`
- name: `SingletonConfigCompatible`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007703c`

## callees

- `0x1800299a4`
- `0x1800bb480`
- `0x1800bc070`
- `0x1800bc07c`
- `0x1800c2644`
- `0x1800c665c`
- `0x180262020`

## string_xrefs

- `0x1800c66c4`: `ID3D12DeviceFactory::CreateDevice: Requested SDK version %d, singleton exists with %d`
- `0x1800c66fc`: `ID3D12DeviceFactory::CreateDevice: Requested debug layer configuration flags (0x%x), mismatches existing singleton's (0x%x)`
- `0x1800c6712`: `ID3D12DeviceFactory::CreateDevice: Requested GPU-based validation to be enabled, and singleton exists with GPU-based validation enabled, but with mismatched GPU-based validation flags (requested 0x%x, singleton has 0x%x)`
- `0x1800c6745`: `ID3D12DeviceFactory::CreateDevice: Requested shader instrumentation state (%s) mismatches existing singleton's state (%s)`
- `0x1800c677b`: `ID3D12DeviceFactory::CreateDevice: Requested DRED support (0x%x) not provided by existing singleton (0x%x).`
- `0x1800c67a8`: `ID3D12DeviceFactory::CreateDevice: Existing singleton device has DRED flags (0x%x) which limit functionality below what was requested (0x%x).`
- `0x1800c67c7`: `ID3D12DeviceFactory::CreateDevice: Requested auto debug name, but existing singleton does not have that enabled.`
- `0x1800c67e8`: `ID3D12DeviceFactory::CreateDevice: Requested dynamic shader linking fallback force disable, but existing singleton doesn't have that set.`
- `0x1800c67fa`: `ID3D12DeviceFactory::CreateDevice: Requested dynamic shader linking fallback force enable, but existing singleton doesn't have that set.`
- `0x1800c6962`: `ID3D12DeviceFactory::CreateDevice: Requested experimental feature {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x} but existing singleton does not have it enabled.`

## pseudocode

```c
bool __fastcall SingletonConfigCompatible(__int64 a1, __int64 a2, __int64 a3)
{
  char *v7; // rsi
  char *v8; // rbx
  _OWORD *v9; // r14
  _OWORD *v10; // rdi
  _OWORD *v11; // r12
  bool v12; // sf
  char *v13; // rax
  size_t v14; // rsi
  _BYTE *v15; // r12
  _BYTE *i; // r14
  _DWORD v17[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v18; // [rsp+7Ch] [rbp-84h]
  _DWORD v19[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v20; // [rsp+8Ch] [rbp-74h]
  _OWORD Buf1[7]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD Buf2[7]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v23[112]; // [rsp+170h] [rbp+70h] BYREF

  (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a2 + 24LL))(a2, v17);
  (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a3 + 24LL))(a3, v19);
  if ( v17[2] > v19[2] )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested SDK version %d, singleton exists with %d");
    return 0;
  }
  if ( (v17[0] & 0x407) != (v19[0] & 0x407) )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested debug layer configuration flags (0x%x), mismatches existing singleton's (0x%x)");
    return 0;
  }
  if ( v17[1] != v19[1] )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested GPU-based validation to be enabled, and singleton exists with GPU-bas"
      "ed validation enabled, but with mismatched GPU-based validation flags (requested 0x%x, singleton has 0x%x)");
    return 0;
  }
  if ( (v17[0] & 0x100) != (v19[0] & 0x100) )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested shader instrumentation state (%s) mismatches existing singleton's state (%s)");
    return 0;
  }
  if ( (~v19[0] & v17[0] & 0x78) != 0 )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested DRED support (0x%x) not provided by existing singleton (0x%x).");
    return 0;
  }
  if ( (~v17[0] & v19[0] & 0x80) != 0 )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Existing singleton device has DRED flags (0x%x) which limit functionality below"
      " what was requested (0x%x).");
    return 0;
  }
  if ( (v19[0] & 0x200) == 0 && (v17[0] & 0x200) != 0 )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested auto debug name, but existing singleton does not have that enabled.");
    return 0;
  }
  if ( ((v17[0] ^ v19[0]) & 0x1000) != 0 )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested dynamic shader linking fallback force disable, but existing singleton"
      " doesn't have that set.");
    return 0;
  }
  if ( ((LOWORD(v17[0]) ^ LOWORD(v19[0])) & 0x800) != 0 )
  {
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested dynamic shader linking fallback force enable, but existing singleton "
      "doesn't have that set.");
    return 0;
  }
  (*(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, Buf1, v18);
  (*(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)a3 + 32LL))(a3, Buf2, v20);
  std::_Sort_unchecked<_GUID *,std::less<void>>(Buf1, &Buf1[v18], v18, 0);
  std::_Sort_unchecked<_GUID *,std::less<void>>(Buf2, &Buf2[v20], v20, 0);
  v7 = (char *)&Buf1[v18];
  v8 = (char *)Buf1;
  v9 = Buf2;
  v10 = v23;
  v11 = &Buf2[v20];
  if ( Buf1 != (_OWORD *)v7 )
  {
    do
    {
      if ( v9 == v11 )
        break;
      if ( memcmp_0(v8, v9, 0x10u) >= 0 )
      {
        v12 = memcmp_0(v9, v8, 0x10u) < 0;
        v13 = v8 + 16;
        ++v9;
        if ( v12 )
          v13 = v8;
        v8 = v13;
      }
      else
      {
        *v10++ = *(_OWORD *)v8;
        v8 += 16;
      }
    }
    while ( v8 != v7 );
  }
  v14 = v7 - v8;
  memcpy_0(v10, v8, v14);
  v15 = (char *)v10 + v14;
  for ( i = v23; i != v15; i += 16 )
    DebugPrintF::operator()(
      a1,
      0,
      "ID3D12DeviceFactory::CreateDevice: Requested experimental feature {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02"
      "x} but existing singleton does not have it enabled.",
      *(_DWORD *)i,
      *((unsigned __int16 *)i + 2),
      *((unsigned __int16 *)i + 3),
      (unsigned __int8)i[8],
      (unsigned __int8)i[9],
      (unsigned __int8)i[10],
      (unsigned __int8)i[11],
      (unsigned __int8)i[12],
      (unsigned __int8)i[13],
      (unsigned __int8)i[14],
      (unsigned __int8)i[15]);
  return v15 == v23;
}

```

## disassembly

```asm
0x1800c665c  push    rbp
0x1800c665e  push    rbx
0x1800c665f  push    rsi
0x1800c6660  push    rdi
0x1800c6661  push    r12
0x1800c6663  push    r14
0x1800c6665  push    r15
0x1800c6667  lea     rbp, [rsp-0F0h]
0x1800c666f  sub     rsp, 1F0h
0x1800c6676  mov     rax, cs:__security_cookie
0x1800c667d  xor     rax, rsp
0x1800c6680  mov     [rbp+120h+var_40], rax
0x1800c6687  mov     rax, [rdx]
0x1800c668a  mov     rbx, rdx
0x1800c668d  mov     r15, rcx
0x1800c6690  lea     rdx, [rsp+220h+var_1B0]
0x1800c6695  mov     rcx, rbx
0x1800c6698  mov     rdi, r8
0x1800c669b  mov     rax, [rax+18h]
0x1800c669f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c66a4  mov     rax, [rdi]
0x1800c66a7  lea     rdx, [rbp+120h+var_1A0]
0x1800c66ab  mov     rcx, rdi
0x1800c66ae  mov     rax, [rax+18h]
0x1800c66b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c66b7  mov     r9d, [rsp+220h+var_1A8]
0x1800c66bc  mov     eax, [rbp+120h+var_198]
0x1800c66bf  cmp     r9d, eax
0x1800c66c2  jbe     short loc_1800C66E0
0x1800c66c4  lea     r8, aId3d12devicefa_0; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c66cb  mov     dword ptr [rsp+220h+var_200], eax
0x1800c66cf  xor     edx, edx
0x1800c66d1  mov     rcx, r15
0x1800c66d4  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800c66d9  xor     al, al
0x1800c66db  jmp     loc_1800C699F
0x1800c66e0  mov     edx, [rbp+120h+var_1A0]
0x1800c66e3  mov     ecx, 407h
0x1800c66e8  mov     r8d, [rsp+220h+var_1B0]
0x1800c66ed  mov     eax, edx
0x1800c66ef  mov     r9d, r8d
0x1800c66f2  and     eax, ecx
0x1800c66f4  and     r9d, ecx
0x1800c66f7  cmp     r9d, eax
0x1800c66fa  jz      short loc_1800C6705
0x1800c66fc  lea     r8, aId3d12devicefa; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c6703  jmp     short loc_1800C66CB
0x1800c6705  mov     r9d, [rsp+220h+var_1AC]
0x1800c670a  mov     eax, [rbp+120h+var_19C]
0x1800c670d  cmp     r9d, eax
0x1800c6710  jz      short loc_1800C671B
0x1800c6712  lea     r8, aId3d12devicefa_7; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c6719  jmp     short loc_1800C66CB
0x1800c671b  mov     eax, 100h
0x1800c6720  mov     ecx, edx
0x1800c6722  mov     r10d, r8d
0x1800c6725  and     ecx, eax
0x1800c6727  and     r10d, eax
0x1800c672a  cmp     r10d, ecx
0x1800c672d  jz      short loc_1800C6768
0x1800c672f  test    ecx, ecx
0x1800c6731  lea     rdx, aDisabled; "disabled"
0x1800c6738  lea     r9, aEnabled; "enabled"
0x1800c673f  mov     rcx, r15
0x1800c6742  mov     rax, r9
0x1800c6745  lea     r8, aId3d12devicefa_10; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c674c  cmovz   rax, rdx
0x1800c6750  test    r10d, r10d
0x1800c6753  mov     [rsp+220h+var_200], rax
0x1800c6758  cmovz   r9, rdx
0x1800c675c  xor     edx, edx
0x1800c675e  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800c6763  jmp     loc_1800C66D9
0x1800c6768  mov     r9d, r8d
0x1800c676b  mov     eax, edx
0x1800c676d  and     r9d, 78h
0x1800c6771  not     eax
0x1800c6773  test    r9d, eax
0x1800c6776  jz      short loc_1800C678B
0x1800c6778  and     edx, 78h
0x1800c677b  lea     r8, aId3d12devicefa_6; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c6782  mov     dword ptr [rsp+220h+var_200], edx
0x1800c6786  jmp     loc_1800C66CF
0x1800c678b  mov     r9d, edx
0x1800c678e  mov     ecx, 80h
0x1800c6793  mov     eax, r8d
0x1800c6796  and     r9d, ecx
0x1800c6799  not     eax
0x1800c679b  test    r9d, eax
0x1800c679e  jz      short loc_1800C67B4
0x1800c67a0  and     r8d, ecx
0x1800c67a3  mov     dword ptr [rsp+220h+var_200], r8d
0x1800c67a8  lea     r8, aId3d12devicefa_1; "ID3D12DeviceFactory::CreateDevice: Exis"...
0x1800c67af  jmp     loc_1800C66CF
0x1800c67b4  bt      edx, 9
0x1800c67b8  setnb   cl
0x1800c67bb  bt      r8d, 9
0x1800c67c0  setb    al
0x1800c67c3  test    al, cl
0x1800c67c5  jz      short loc_1800C67DD
0x1800c67c7  lea     r8, aId3d12devicefa_8; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c67ce  xor     edx, edx
0x1800c67d0  mov     rcx, r15
0x1800c67d3  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800c67d8  jmp     loc_1800C66D9
0x1800c67dd  mov     eax, edx
0x1800c67df  xor     eax, r8d
0x1800c67e2  bt      eax, 0Ch
0x1800c67e6  jnb     short loc_1800C67F1
0x1800c67e8  lea     r8, aId3d12devicefa_11; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c67ef  jmp     short loc_1800C67CE
0x1800c67f1  xor     edx, r8d
0x1800c67f4  bt      edx, 0Bh
0x1800c67f8  jnb     short loc_1800C6803
0x1800c67fa  lea     r8, aId3d12devicefa_3; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c6801  jmp     short loc_1800C67CE
0x1800c6803  mov     rax, [rbx]
0x1800c6806  lea     rdx, [rbp+120h+Buf1]
0x1800c680a  mov     r8d, [rsp+220h+var_1A4]
0x1800c680f  mov     rcx, rbx
0x1800c6812  mov     rax, [rax+20h]
0x1800c6816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c681b  mov     rax, [rdi]
0x1800c681e  lea     rdx, [rbp+120h+Buf2]
0x1800c6822  mov     r8d, [rbp+120h+var_194]
0x1800c6826  mov     rcx, rdi
0x1800c6829  mov     rax, [rax+20h]
0x1800c682d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6832  mov     r8d, [rsp+220h+var_1A4]
0x1800c6837  lea     rdx, [rbp+120h+Buf1]
0x1800c683b  mov     eax, r8d
0x1800c683e  lea     rcx, [rbp+120h+Buf1]
0x1800c6842  shl     rax, 4
0x1800c6846  xor     r9d, r9d
0x1800c6849  add     rdx, rax
0x1800c684c  call    ??$_Sort_unchecked@PEAU_GUID@@U?$less@X@std@@@std@@YAXPEAU_GUID@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<_GUID *,std::less<void>>(_GUID *,_GUID *,__int64,std::less<void>)
0x1800c6851  mov     r8d, [rbp+120h+var_194]
0x1800c6855  lea     rdx, [rbp+120h+Buf2]
0x1800c6859  mov     eax, r8d
0x1800c685c  lea     rcx, [rbp+120h+Buf2]
0x1800c6860  shl     rax, 4
0x1800c6864  xor     r9d, r9d
0x1800c6867  add     rdx, rax
0x1800c686a  call    ??$_Sort_unchecked@PEAU_GUID@@U?$less@X@std@@@std@@YAXPEAU_GUID@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<_GUID *,std::less<void>>(_GUID *,_GUID *,__int64,std::less<void>)
0x1800c686f  mov     eax, [rsp+220h+var_1A4]
0x1800c6873  lea     rsi, [rbp+120h+Buf1]
0x1800c6877  shl     rax, 4
0x1800c687b  lea     r12, [rbp+120h+Buf2]
0x1800c687f  add     rsi, rax
0x1800c6882  lea     rbx, [rbp+120h+Buf1]
0x1800c6886  mov     eax, [rbp+120h+var_194]
0x1800c6889  lea     r14, [rbp+120h+Buf2]
0x1800c688d  shl     rax, 4
0x1800c6891  lea     rdi, [rbp+120h+var_B0]
0x1800c6895  add     r12, rax
0x1800c6898  lea     rax, [rbp+120h+Buf1]
0x1800c689c  cmp     rax, rsi
0x1800c689f  jz      short loc_1800C68F8
0x1800c68a1  cmp     r14, r12
0x1800c68a4  jz      short loc_1800C68F8
0x1800c68a6  mov     r8d, 10h; Size
0x1800c68ac  mov     rdx, r14; Buf2
0x1800c68af  mov     rcx, rbx; Buf1
0x1800c68b2  call    memcmp_0
0x1800c68b7  test    eax, eax
0x1800c68b9  jns     short loc_1800C68CC
0x1800c68bb  movups  xmm0, xmmword ptr [rbx]
0x1800c68be  movdqu  xmmword ptr [rdi], xmm0
0x1800c68c2  add     rdi, 10h
0x1800c68c6  add     rbx, 10h
0x1800c68ca  jmp     short loc_1800C68F3
0x1800c68cc  mov     r8d, 10h; Size
0x1800c68d2  mov     rdx, rbx; Buf2
0x1800c68d5  mov     rcx, r14; Buf1
0x1800c68d8  call    memcmp_0
0x1800c68dd  test    eax, eax
0x1800c68df  lea     rax, [rbx+10h]
0x1800c68e3  sets    cl
0x1800c68e6  add     r14, 10h
0x1800c68ea  test    cl, cl
0x1800c68ec  cmovnz  rax, rbx
0x1800c68f0  mov     rbx, rax
0x1800c68f3  cmp     rbx, rsi
0x1800c68f6  jnz     short loc_1800C68A1
0x1800c68f8  sub     rsi, rbx
0x1800c68fb  mov     rdx, rbx; Src
0x1800c68fe  mov     r8, rsi; Size
0x1800c6901  mov     rcx, rdi; void *
0x1800c6904  call    memcpy_0
0x1800c6909  lea     rax, [rbp+120h+var_B0]
0x1800c690d  lea     r12, [rsi+rdi]
0x1800c6911  lea     r14, [rbp+120h+var_B0]
0x1800c6915  cmp     rax, r12
0x1800c6918  jz      short loc_1800C6995
0x1800c691a  movzx   r9d, byte ptr [r14+0Bh]
0x1800c691f  movzx   eax, byte ptr [r14+0Fh]
0x1800c6924  movzx   ecx, byte ptr [r14+0Eh]
0x1800c6929  movzx   edx, byte ptr [r14+0Dh]
0x1800c692e  movzx   r8d, byte ptr [r14+0Ch]
0x1800c6933  movzx   r10d, byte ptr [r14+0Ah]
0x1800c6938  movzx   r11d, byte ptr [r14+9]
0x1800c693d  movzx   ebx, byte ptr [r14+8]
0x1800c6942  movzx   edi, word ptr [r14+6]
0x1800c6947  movzx   esi, word ptr [r14+4]
0x1800c694c  mov     [rsp+220h+var_1B8], eax
0x1800c6950  mov     [rsp+220h+var_1C0], ecx
0x1800c6954  mov     rcx, r15
0x1800c6957  mov     [rsp+220h+var_1C8], edx
0x1800c695b  xor     edx, edx
0x1800c695d  mov     [rsp+220h+var_1D0], r8d
0x1800c6962  lea     r8, aId3d12devicefa_4; "ID3D12DeviceFactory::CreateDevice: Requ"...
0x1800c6969  mov     [rsp+220h+var_1D8], r9d
0x1800c696e  mov     r9d, [r14]
0x1800c6971  mov     [rsp+220h+var_1E0], r10d
0x1800c6976  mov     [rsp+220h+var_1E8], r11d
0x1800c697b  mov     [rsp+220h+var_1F0], ebx
0x1800c697f  mov     [rsp+220h+var_1F8], edi
0x1800c6983  mov     dword ptr [rsp+220h+var_200], esi
0x1800c6987  call    ??RDebugPrintF@@QEAAXIPEBDZZ; DebugPrintF::operator()(uint,char const *,...)
0x1800c698c  add     r14, 10h
0x1800c6990  cmp     r14, r12
0x1800c6993  jnz     short loc_1800C691A
0x1800c6995  lea     rax, [rbp+120h+var_B0]
0x1800c6999  cmp     r12, rax
0x1800c699c  setz    al
0x1800c699f  mov     rcx, [rbp+120h+var_40]
0x1800c69a6  xor     rcx, rsp; StackCookie
0x1800c69a9  call    __security_check_cookie
0x1800c69ae  add     rsp, 1F0h
0x1800c69b5  pop     r15
0x1800c69b7  pop     r14
0x1800c69b9  pop     r12
0x1800c69bb  pop     rdi
0x1800c69bc  pop     rsi
0x1800c69bd  pop     rbx
0x1800c69be  pop     rbp
0x1800c69bf  retn
```
