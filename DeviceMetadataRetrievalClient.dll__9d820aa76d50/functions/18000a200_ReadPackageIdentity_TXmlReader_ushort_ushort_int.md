# ReadPackageIdentity(TXmlReader *,ushort * *,ushort * *,int *)

- ea: `0x18000a200`
- end: `0x18000a4bc`
- name: `?ReadPackageIdentity@@YAJPEAVTXmlReader@@PEAPEAG1PEAH@Z`
- size: `700`
- prototype: `__int64 __fastcall(struct TXmlReader *this, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4c4`

## callees

- `0x18000a200`
- `0x18000c17c`
- `0x18000eed0`
- `0x1800108d8`
- `0x180010a30`
- `0x180010a84`
- `0x180014010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a3bd`
- `msvcrt!_wcsicmp` at `0x18000a3d3`
- `msvcrt!_wcsicmp` at `0x18000a3bd`
- `msvcrt!_wcsicmp` at `0x18000a3d3`
- `KERNEL32!GetProcessHeap` at `0x18000a46a`
- `KERNEL32!GetProcessHeap` at `0x18000a483`
- `KERNEL32!GetProcessHeap` at `0x18000a46a`
- `KERNEL32!GetProcessHeap` at `0x18000a483`
- `KERNEL32!HeapFree` at `0x18000a478`
- `KERNEL32!HeapFree` at `0x18000a491`
- `KERNEL32!HeapFree` at `0x18000a478`
- `KERNEL32!HeapFree` at `0x18000a491`

## string_xrefs

- `0x18000a220`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a41f`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a36a`: `AccessCustomDriver`
- `0x18000a3a5`: `AccessCustomDriver`

## pseudocode

```c
__int64 __fastcall ReadPackageIdentity(struct TXmlReader *this, unsigned __int16 **a2, unsigned __int16 **a3, int *a4)
{
  unsigned int IsNodeQName; // ebx
  const unsigned __int16 *v9; // r8
  _QWORD *v10; // rcx
  int v11; // edx
  const unsigned __int16 *v12; // r9
  unsigned __int16 *v13; // rbp
  const unsigned __int16 *v14; // r8
  int v15; // r8d
  unsigned __int16 *v16; // rdi
  _QWORD *v17; // rcx
  int v18; // edx
  const unsigned __int16 *v19; // r9
  const unsigned __int16 *v20; // r8
  int v21; // esi
  unsigned int AttributeString; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v24; // rax
  wchar_t *String1[11]; // [rsp+30h] [rbp-58h] BYREF

  String1[0] = 0;
  IsNodeQName = TXmlReader::IsNodeQName(
                  this,
                  L"Identity",
                  L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
  if ( IsNodeQName == 1 )
    return 0;
  if ( IsNodeQName )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 99;
      v12 = L"Identity";
LABEL_7:
      WPP_SF_Sd(v10[2], v11, (_DWORD)v9, (_DWORD)v12, IsNodeQName);
      return IsNodeQName;
    }
    return IsNodeQName;
  }
  IsNodeQName = TXmlReader::ReadAttributeString(this, L"Name", v9, (const unsigned __int16 **)String1);
  if ( !IsNodeQName )
  {
    v13 = MemMallocAndCopy(String1[0]);
    if ( !v13 )
      return (unsigned int)-2147024882;
    IsNodeQName = TXmlReader::ReadAttributeString(this, L"Publisher", v14, (const unsigned __int16 **)String1);
    if ( IsNodeQName )
    {
      v16 = 0;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 101;
        v19 = L"Publisher";
LABEL_38:
        WPP_SF_Sd(v17[2], v18, v15, (_DWORD)v19, IsNodeQName);
        goto LABEL_39;
      }
      goto LABEL_39;
    }
    v16 = MemMallocAndCopy(String1[0]);
    if ( !v16 )
    {
      IsNodeQName = -2147024882;
      goto LABEL_39;
    }
    v21 = 0;
    if ( a4 )
    {
      AttributeString = TXmlReader::ReadAttributeString(
                          this,
                          L"AccessCustomDriver",
                          v20,
                          (const unsigned __int16 **)String1);
      IsNodeQName = AttributeString;
      if ( AttributeString != 1 )
      {
        if ( AttributeString )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v18 = 102;
            v19 = L"AccessCustomDriver";
            goto LABEL_38;
          }
LABEL_39:
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
          if ( v16 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v16);
          }
          return IsNodeQName;
        }
        if ( !_wcsicmp(String1[0], L"true") || !_wcsicmp(String1[0], L"1") )
          v21 = 1;
      }
    }
    IsNodeQName = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 88LL))(*(_QWORD *)this);
    if ( IsNodeQName )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v18 = 103;
    }
    else
    {
      IsNodeQName = TXmlReader::ReadElementString(
                      this,
                      L"Identity",
                      L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo",
                      (const unsigned __int16 **)String1);
      if ( !IsNodeQName )
      {
        *a2 = v13;
        *a3 = v16;
        if ( a4 )
          *a4 = v21;
        return IsNodeQName;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v18 = 104;
    }
    v19 = L"Identity";
    goto LABEL_38;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 100;
    v12 = L"Name";
    goto LABEL_7;
  }
  return IsNodeQName;
}

```

## disassembly

```asm
0x18000a200  push    rbx
0x18000a202  push    rbp
0x18000a203  push    rsi
0x18000a204  push    rdi
0x18000a205  push    r12
0x18000a207  push    r13
0x18000a209  push    r14
0x18000a20b  push    r15
0x18000a20d  sub     rsp, 48h
0x18000a211  mov     r12, r8
0x18000a214  mov     [rsp+88h+String1], 0
0x18000a21d  mov     r13, rdx
0x18000a220  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a227  lea     rdx, aIdentity; "Identity"
0x18000a22e  mov     r15, r9
0x18000a231  mov     r14, rcx
0x18000a234  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x18000a239  mov     ebx, eax
0x18000a23b  cmp     eax, 1
0x18000a23e  jnz     short loc_18000A247
0x18000a240  xor     ebx, ebx
0x18000a242  jmp     loc_18000A4A9
0x18000a247  test    ebx, ebx
0x18000a249  jz      short loc_18000A28A
0x18000a24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a252  lea     rax, WPP_GLOBAL_Control
0x18000a259  cmp     rcx, rax
0x18000a25c  jz      loc_18000A4A9
0x18000a262  test    byte ptr [rcx+1Ch], 1
0x18000a266  jz      loc_18000A4A9
0x18000a26c  mov     edx, 63h ; 'c'
0x18000a271  lea     r9, aIdentity; "Identity"
0x18000a278  mov     rcx, [rcx+10h]
0x18000a27c  mov     [rsp+88h+var_68], ebx
0x18000a280  call    WPP_SF_Sd
0x18000a285  jmp     loc_18000A4A9
0x18000a28a  lea     r9, [rsp+88h+String1]; unsigned __int16 **
0x18000a28f  mov     rcx, r14; this
0x18000a292  lea     rdx, aName; "Name"
0x18000a299  call    ?ReadAttributeString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadAttributeString(ushort const *,ushort const *,ushort const * *)
0x18000a29e  mov     ebx, eax
0x18000a2a0  test    eax, eax
0x18000a2a2  jz      short loc_18000A2D3
0x18000a2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2ab  lea     rax, WPP_GLOBAL_Control
0x18000a2b2  cmp     rcx, rax
0x18000a2b5  jz      loc_18000A4A9
0x18000a2bb  test    byte ptr [rcx+1Ch], 1
0x18000a2bf  jz      loc_18000A4A9
0x18000a2c5  mov     edx, 64h ; 'd'
0x18000a2ca  lea     r9, aName; "Name"
0x18000a2d1  jmp     short loc_18000A278
0x18000a2d3  mov     rcx, [rsp+88h+String1]; unsigned __int16 *
0x18000a2d8  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000a2dd  mov     rbp, rax
0x18000a2e0  test    rax, rax
0x18000a2e3  jnz     short loc_18000A2EF
0x18000a2e5  mov     ebx, 8007000Eh
0x18000a2ea  jmp     loc_18000A4A9
0x18000a2ef  lea     r9, [rsp+88h+String1]; unsigned __int16 **
0x18000a2f4  mov     rcx, r14; this
0x18000a2f7  lea     rdx, aPublisher; "Publisher"
0x18000a2fe  call    ?ReadAttributeString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadAttributeString(ushort const *,ushort const *,ushort const * *)
0x18000a303  mov     ebx, eax
0x18000a305  test    eax, eax
0x18000a307  jz      short loc_18000A33B
0x18000a309  xor     edi, edi
0x18000a30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a312  lea     rax, WPP_GLOBAL_Control
0x18000a319  cmp     rcx, rax
0x18000a31c  jz      loc_18000A46A
0x18000a322  test    byte ptr [rcx+1Ch], 1
0x18000a326  jz      loc_18000A46A
0x18000a32c  lea     edx, [rdi+65h]
0x18000a32f  lea     r9, aPublisher; "Publisher"
0x18000a336  jmp     loc_18000A45D
0x18000a33b  mov     rcx, [rsp+88h+String1]; unsigned __int16 *
0x18000a340  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000a345  mov     rdi, rax
0x18000a348  test    rax, rax
0x18000a34b  jnz     short loc_18000A357
0x18000a34d  mov     ebx, 8007000Eh
0x18000a352  jmp     loc_18000A46A
0x18000a357  xor     esi, esi
0x18000a359  test    r15, r15
0x18000a35c  jz      loc_18000A3E2
0x18000a362  lea     r9, [rsp+88h+String1]; unsigned __int16 **
0x18000a367  mov     rcx, r14; this
0x18000a36a  lea     rdx, aAccesscustomdr; "AccessCustomDriver"
0x18000a371  call    ?ReadAttributeString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadAttributeString(ushort const *,ushort const *,ushort const * *)
0x18000a376  mov     ebx, eax
0x18000a378  cmp     eax, 1
0x18000a37b  jz      short loc_18000A3E2
0x18000a37d  test    eax, eax
0x18000a37f  jz      short loc_18000A3B1
0x18000a381  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a388  lea     rax, WPP_GLOBAL_Control
0x18000a38f  cmp     rcx, rax
0x18000a392  jz      loc_18000A46A
0x18000a398  test    byte ptr [rcx+1Ch], 1
0x18000a39c  jz      loc_18000A46A
0x18000a3a2  lea     edx, [rsi+66h]
0x18000a3a5  lea     r9, aAccesscustomdr; "AccessCustomDriver"
0x18000a3ac  jmp     loc_18000A45D
0x18000a3b1  mov     rcx, [rsp+88h+String1]; String1
0x18000a3b6  lea     rdx, aTrue; "true"
0x18000a3bd  call    cs:__imp__wcsicmp
0x18000a3c3  test    eax, eax
0x18000a3c5  jz      short loc_18000A3DD
0x18000a3c7  mov     rcx, [rsp+88h+String1]; String1
0x18000a3cc  lea     rdx, a1; "1"
0x18000a3d3  call    cs:__imp__wcsicmp
0x18000a3d9  test    eax, eax
0x18000a3db  jnz     short loc_18000A3E2
0x18000a3dd  mov     esi, 1
0x18000a3e2  mov     rcx, [r14]
0x18000a3e5  mov     rax, [rcx]
0x18000a3e8  mov     rax, [rax+58h]
0x18000a3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f1  mov     ebx, eax
0x18000a3f3  test    eax, eax
0x18000a3f5  jz      short loc_18000A417
0x18000a3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3fe  lea     rax, WPP_GLOBAL_Control
0x18000a405  cmp     rcx, rax
0x18000a408  jz      short loc_18000A46A
0x18000a40a  test    byte ptr [rcx+1Ch], 1
0x18000a40e  jz      short loc_18000A46A
0x18000a410  mov     edx, 67h ; 'g'
0x18000a415  jmp     short loc_18000A456
0x18000a417  lea     r9, [rsp+88h+String1]; unsigned __int16 **
0x18000a41c  mov     rcx, r14; this
0x18000a41f  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a426  lea     rdx, aIdentity; "Identity"
0x18000a42d  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x18000a432  mov     ebx, eax
0x18000a434  test    eax, eax
0x18000a436  jz      short loc_18000A499
0x18000a438  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a43f  lea     rax, WPP_GLOBAL_Control
0x18000a446  cmp     rcx, rax
0x18000a449  jz      short loc_18000A46A
0x18000a44b  test    byte ptr [rcx+1Ch], 1
0x18000a44f  jz      short loc_18000A46A
0x18000a451  mov     edx, 68h ; 'h'
0x18000a456  lea     r9, aIdentity; "Identity"
0x18000a45d  mov     rcx, [rcx+10h]
0x18000a461  mov     [rsp+88h+var_68], ebx
0x18000a465  call    WPP_SF_Sd
0x18000a46a  call    cs:__imp_GetProcessHeap
0x18000a470  mov     r8, rbp; lpMem
0x18000a473  xor     edx, edx; dwFlags
0x18000a475  mov     rcx, rax; hHeap
0x18000a478  call    cs:__imp_HeapFree
0x18000a47e  test    rdi, rdi
0x18000a481  jz      short loc_18000A4A9
0x18000a483  call    cs:__imp_GetProcessHeap
0x18000a489  mov     r8, rdi; lpMem
0x18000a48c  xor     edx, edx; dwFlags
0x18000a48e  mov     rcx, rax; hHeap
0x18000a491  call    cs:__imp_HeapFree
0x18000a497  jmp     short loc_18000A4A9
0x18000a499  mov     [r13+0], rbp
0x18000a49d  mov     [r12], rdi
0x18000a4a1  test    r15, r15
0x18000a4a4  jz      short loc_18000A4A9
0x18000a4a6  mov     [r15], esi
0x18000a4a9  mov     eax, ebx
0x18000a4ab  add     rsp, 48h
0x18000a4af  pop     r15
0x18000a4b1  pop     r14
0x18000a4b3  pop     r13
0x18000a4b5  pop     r12
0x18000a4b7  pop     rdi
0x18000a4b8  pop     rsi
0x18000a4b9  pop     rbp
0x18000a4ba  pop     rbx
0x18000a4bb  retn
```
