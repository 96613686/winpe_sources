# MidiEndpointTable::AddCreatedEndpointDevice(MidiVirtualDeviceEndpointEntry &)

- ea: `0x180014ab0`
- end: `0x180014db1`
- name: `?AddCreatedEndpointDevice@MidiEndpointTable@@QEAAJAEAUMidiVirtualDeviceEndpointEntry@@@Z`
- size: `769`
- prototype: `__int64 __fastcall(MidiEndpointTable *__hidden this, struct MidiVirtualDeviceEndpointEntry *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000e0a4`

## callees

- `0x18000163c`
- `0x1800038f0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000bf6c`
- `0x18000d1ac`
- `0x18000d86c`
- `0x1800117d8`
- `0x1800146f4`
- `0x180014830`
- `0x180014ab0`
- `0x180019850`
- `0x180021010`

## string_xrefs

- `0x180014c83`: `MidiEndpointTable::AddCreatedEndpointDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MidiEndpointTable::AddCreatedEndpointDevice(
        MidiEndpointTable *this,
        struct MidiVirtualDeviceEndpointEntry *a2)
{
  _DWORD *v4; // r14
  const wchar_t *v5; // rax
  const wchar_t *v6; // rcx
  const wchar_t *v7; // r8
  const wchar_t *v8; // r9
  const wchar_t *v9; // rdi
  const wchar_t *v10; // rsi
  int v11; // r10d
  __int64 v12; // rdx
  __int64 v13; // r11
  int v14; // r11d
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  __int64 v27; // rax
  int v29; // [rsp+20h] [rbp-E0h]
  MidiEndpointTable *v30; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v31[32]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v32[40]; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+80h] [rbp-80h] BYREF
  const char *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  MidiEndpointTable **v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  const wchar_t *v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+CCh] [rbp-34h]
  const wchar_t *v41; // [rsp+D0h] [rbp-30h]
  int v42; // [rsp+D8h] [rbp-28h]
  int v43; // [rsp+DCh] [rbp-24h]
  const wchar_t *v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+ECh] [rbp-14h]
  const wchar_t *v47; // [rsp+F0h] [rbp-10h]
  int v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+FCh] [rbp-4h]
  const wchar_t *v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+108h] [rbp+8h]
  int v52; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+118h] [rbp+18h]
  int v55; // [rsp+11Ch] [rbp+1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v5 = (const wchar_t *)((char *)a2 + 256);
    if ( *((_QWORD *)a2 + 35) > 7u )
      v5 = *(const wchar_t **)v5;
    v6 = (const wchar_t *)((char *)a2 + 160);
    if ( *((_QWORD *)a2 + 23) > 7u )
      v6 = *(const wchar_t **)v6;
    v7 = (const wchar_t *)((char *)a2 + 224);
    if ( *((_QWORD *)a2 + 31) > 7u )
      v7 = *(const wchar_t **)v7;
    v8 = (const wchar_t *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v8 = *(const wchar_t **)v8;
    v9 = (const wchar_t *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 7) > 7u )
      v9 = *(const wchar_t **)v9;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v10 = (const wchar_t *)a2;
    else
      v10 = *(const wchar_t **)a2;
    v30 = this;
    v11 = 2;
    v12 = -1;
    if ( v5 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v5[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
      v5 = &S2;
      v14 = 2;
    }
    v53 = v5;
    v54 = v14;
    v55 = 0;
    if ( v6 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v6[v15] );
      v16 = 2 * v15 + 2;
    }
    else
    {
      v6 = &S2;
      v16 = 2;
    }
    v50 = v6;
    v51 = v16;
    v52 = 0;
    if ( v7 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v7 = &S2;
      v18 = 2;
    }
    v47 = v7;
    v48 = v18;
    v49 = 0;
    if ( v8 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v8[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v8 = &S2;
      v20 = 2;
    }
    v44 = v8;
    v45 = v20;
    v46 = 0;
    if ( v9 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v9[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v9 = &S2;
      v22 = 2;
    }
    v41 = v9;
    v42 = v22;
    v43 = 0;
    if ( v10 )
    {
      do
        ++v12;
      while ( v10[v12] );
      v11 = 2 * v12 + 2;
    }
    else
    {
      v10 = &S2;
    }
    v38 = v10;
    v39 = v11;
    v40 = 0;
    v36 = &v30;
    v37 = 8;
    v34 = "MidiEndpointTable::AddCreatedEndpointDevice";
    v35 = 44;
    tlgWriteTransfer_EventWriteTransfer((__int64)v4, (unsigned __int8 *)qword_180026F88, 0, 0, 0xAu, &v33);
  }
  v23 = std::wstring::wstring(v31, a2);
  WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(v32, v23);
  std::wstring::operator=(a2, v32);
  v24 = *((_QWORD *)a2 + 38);
  *((_QWORD *)a2 + 38) = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = *((_QWORD *)a2 + 37);
  *((_QWORD *)a2 + 37) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(
    (char *)this + 40,
    &v30,
    v32);
  if ( v30 == *((MidiEndpointTable **)this + 5) )
  {
    v27 = std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[]((char *)this + 40, v32);
    MidiVirtualDeviceEndpointEntry::operator=(v27, a2);
    v26 = 0;
  }
  else
  {
    v26 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midiendpointtable.cpp",
      (const char *)0x80070057LL,
      v29);
  }
  std::wstring::~wstring(v32);
  return v26;
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp-8+arg_10], rbx
0x180014ab5  push    rbp
0x180014ab6  push    rsi
0x180014ab7  push    rdi
0x180014ab8  push    r12
0x180014aba  push    r13
0x180014abc  push    r14
0x180014abe  push    r15
0x180014ac0  lea     rbp, [rsp-30h]
0x180014ac5  sub     rsp, 130h
0x180014acc  mov     rax, cs:__security_cookie
0x180014ad3  xor     rax, rsp
0x180014ad6  mov     [rbp+60h+var_40], rax
0x180014ada  mov     rbx, rdx
0x180014add  mov     r15, rcx
0x180014ae0  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180014ae5  mov     r14, [rax+8]
0x180014ae9  mov     eax, [r14]
0x180014aec  xor     r12d, r12d
0x180014aef  cmp     eax, 4
0x180014af2  jbe     loc_180014CBC
0x180014af8  lea     rax, [rbx+100h]
0x180014aff  cmp     qword ptr [rax+18h], 7
0x180014b04  jbe     short loc_180014B09
0x180014b06  mov     rax, [rax]
0x180014b09  lea     rcx, [rbx+0A0h]
0x180014b10  cmp     qword ptr [rcx+18h], 7
0x180014b15  jbe     short loc_180014B1A
0x180014b17  mov     rcx, [rcx]
0x180014b1a  lea     r8, [rbx+0E0h]
0x180014b21  cmp     qword ptr [r8+18h], 7
0x180014b26  jbe     short loc_180014B2B
0x180014b28  mov     r8, [r8]
0x180014b2b  lea     r9, [rbx+60h]
0x180014b2f  cmp     qword ptr [r9+18h], 7
0x180014b34  jbe     short loc_180014B39
0x180014b36  mov     r9, [r9]
0x180014b39  lea     rdi, [rbx+20h]
0x180014b3d  cmp     qword ptr [rdi+18h], 7
0x180014b42  jbe     short loc_180014B47
0x180014b44  mov     rdi, [rdi]
0x180014b47  cmp     qword ptr [rbx+18h], 7
0x180014b4c  jbe     short loc_180014B53
0x180014b4e  mov     rsi, [rbx]
0x180014b51  jmp     short loc_180014B56
0x180014b53  mov     rsi, rbx
0x180014b56  mov     [rsp+160h+var_130], r15
0x180014b5b  lea     r13, S2
0x180014b62  mov     r10d, 2
0x180014b68  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014b6c  test    rax, rax
0x180014b6f  jz      short loc_180014B88
0x180014b71  mov     r11, rdx
0x180014b74  inc     r11
0x180014b77  cmp     [rax+r11*2], r12w
0x180014b7c  jnz     short loc_180014B74
0x180014b7e  lea     r11d, ds:2[r11*2]
0x180014b86  jmp     short loc_180014B8E
0x180014b88  mov     rax, r13
0x180014b8b  mov     r11d, r10d
0x180014b8e  mov     [rbp+60h+var_50], rax
0x180014b92  mov     [rbp+60h+var_48], r11d
0x180014b96  mov     [rbp+60h+var_44], r12d
0x180014b9a  test    rcx, rcx
0x180014b9d  jz      short loc_180014BB5
0x180014b9f  mov     rax, rdx
0x180014ba2  inc     rax
0x180014ba5  cmp     [rcx+rax*2], r12w
0x180014baa  jnz     short loc_180014BA2
0x180014bac  lea     eax, ds:2[rax*2]
0x180014bb3  jmp     short loc_180014BBB
0x180014bb5  mov     rcx, r13
0x180014bb8  mov     eax, r10d
0x180014bbb  mov     [rbp+60h+var_60], rcx
0x180014bbf  mov     [rbp+60h+var_58], eax
0x180014bc2  mov     [rbp+60h+var_54], r12d
0x180014bc6  test    r8, r8
0x180014bc9  jz      short loc_180014BE1
0x180014bcb  mov     rax, rdx
0x180014bce  inc     rax
0x180014bd1  cmp     [r8+rax*2], r12w
0x180014bd6  jnz     short loc_180014BCE
0x180014bd8  lea     eax, ds:2[rax*2]
0x180014bdf  jmp     short loc_180014BE7
0x180014be1  mov     r8, r13
0x180014be4  mov     eax, r10d
0x180014be7  mov     [rbp+60h+var_70], r8
0x180014beb  mov     [rbp+60h+var_68], eax
0x180014bee  mov     [rbp+60h+var_64], r12d
0x180014bf2  test    r9, r9
0x180014bf5  jz      short loc_180014C0D
0x180014bf7  mov     rax, rdx
0x180014bfa  inc     rax
0x180014bfd  cmp     [r9+rax*2], r12w
0x180014c02  jnz     short loc_180014BFA
0x180014c04  lea     eax, ds:2[rax*2]
0x180014c0b  jmp     short loc_180014C13
0x180014c0d  mov     r9, r13
0x180014c10  mov     eax, r10d
0x180014c13  mov     [rbp+60h+var_80], r9
0x180014c17  mov     [rbp+60h+var_78], eax
0x180014c1a  mov     [rbp+60h+var_74], r12d
0x180014c1e  test    rdi, rdi
0x180014c21  jz      short loc_180014C39
0x180014c23  mov     rax, rdx
0x180014c26  inc     rax
0x180014c29  cmp     [rdi+rax*2], r12w
0x180014c2e  jnz     short loc_180014C26
0x180014c30  lea     eax, ds:2[rax*2]
0x180014c37  jmp     short loc_180014C3F
0x180014c39  mov     rdi, r13
0x180014c3c  mov     eax, r10d
0x180014c3f  mov     [rbp+60h+var_90], rdi
0x180014c43  mov     [rbp+60h+var_88], eax
0x180014c46  mov     [rbp+60h+var_84], r12d
0x180014c4a  test    rsi, rsi
0x180014c4d  jz      short loc_180014C63
0x180014c4f  inc     rdx
0x180014c52  cmp     [rsi+rdx*2], r12w
0x180014c57  jnz     short loc_180014C4F
0x180014c59  lea     r10d, ds:2[rdx*2]
0x180014c61  jmp     short loc_180014C66
0x180014c63  mov     rsi, r13
0x180014c66  mov     [rbp+60h+var_A0], rsi
0x180014c6a  mov     [rbp+60h+var_98], r10d
0x180014c6e  mov     [rbp+60h+var_94], r12d
0x180014c72  lea     rax, [rsp+160h+var_130]
0x180014c77  mov     [rbp+60h+var_B0], rax
0x180014c7b  mov     [rbp+60h+var_A8], 8
0x180014c83  lea     rax, aMidiendpointta_2; "MidiEndpointTable::AddCreatedEndpointDe"...
0x180014c8a  mov     [rbp+60h+var_C0], rax
0x180014c8e  mov     [rbp+60h+var_B8], 2Ch ; ','
0x180014c96  lea     rax, [rbp+60h+var_E0]
0x180014c9a  mov     [rsp+160h+var_138], rax
0x180014c9f  mov     [rsp+160h+var_140], 0Ah; int
0x180014ca7  xor     r9d, r9d
0x180014caa  xor     r8d, r8d
0x180014cad  lea     rdx, qword_180026F88
0x180014cb4  mov     rcx, r14
0x180014cb7  call    _tlgWriteTransfer_EventWriteTransfer
0x180014cbc  mov     rdx, rbx
0x180014cbf  lea     rcx, [rsp+160h+var_128]
0x180014cc4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180014cc9  mov     rdx, rax
0x180014ccc  lea     rcx, [rsp+160h+var_108]
0x180014cd1  call    ?ToUpperTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToUpperTrimmedWStringCopy(std::wstring)
0x180014cd6  lea     rdx, [rsp+160h+var_108]
0x180014cdb  mov     rcx, rbx
0x180014cde  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014ce3  nop
0x180014ce4  mov     rcx, [rbx+130h]
0x180014ceb  mov     [rbx+130h], r12
0x180014cf2  test    rcx, rcx
0x180014cf5  jz      short loc_180014D04
0x180014cf7  mov     rax, [rcx]
0x180014cfa  mov     rax, [rax+10h]
0x180014cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d03  nop
0x180014d04  mov     rcx, [rbx+128h]
0x180014d0b  mov     [rbx+128h], r12
0x180014d12  test    rcx, rcx
0x180014d15  jz      short loc_180014D24
0x180014d17  mov     rax, [rcx]
0x180014d1a  mov     rax, [rax+10h]
0x180014d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d23  nop
0x180014d24  lea     rdi, [r15+28h]
0x180014d28  lea     r8, [rsp+160h+var_108]
0x180014d2d  lea     rdx, [rsp+160h+var_130]
0x180014d32  mov     rcx, rdi
0x180014d35  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::find(std::wstring const &)
0x180014d3a  mov     rax, [rdi]
0x180014d3d  cmp     [rsp+160h+var_130], rax
0x180014d42  jz      short loc_180014D63
0x180014d44  mov     rcx, [rbp+68h]; this
0x180014d48  mov     ebx, 80070057h
0x180014d4d  mov     r9d, ebx; char *
0x180014d50  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\virtualmiditr"...
0x180014d57  mov     edx, 36h ; '6'; void *
0x180014d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d61  jmp     short loc_180014D7E
0x180014d63  lea     rdx, [rsp+160h+var_108]
0x180014d68  mov     rcx, rdi
0x180014d6b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@@std@@QEAAAEAUMidiVirtualDeviceEndpointEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,MidiVirtualDeviceEndpointEntry>::operator[](std::wstring const &)
0x180014d70  mov     rcx, rax
0x180014d73  mov     rdx, rbx
0x180014d76  call    ??4MidiVirtualDeviceEndpointEntry@@QEAAAEAU0@AEBU0@@Z; MidiVirtualDeviceEndpointEntry::operator=(MidiVirtualDeviceEndpointEntry const &)
0x180014d7b  mov     ebx, r12d
0x180014d7e  lea     rcx, [rsp+160h+var_108]
0x180014d83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014d88  mov     eax, ebx
0x180014d8a  mov     rcx, [rbp+60h+var_40]
0x180014d8e  xor     rcx, rsp; StackCookie
0x180014d91  call    __security_check_cookie
0x180014d96  mov     rbx, [rsp+160h+arg_10]
0x180014d9e  add     rsp, 130h
0x180014da5  pop     r15
0x180014da7  pop     r14
0x180014da9  pop     r13
0x180014dab  pop     r12
0x180014dad  pop     rdi
0x180014dae  pop     rsi
0x180014daf  pop     rbp
0x180014db0  retn
```
