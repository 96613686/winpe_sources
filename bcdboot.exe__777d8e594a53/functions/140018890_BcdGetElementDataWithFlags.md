# BcdGetElementDataWithFlags

- ea: `0x140018890`
- end: `0x140018b4c`
- name: `BcdGetElementDataWithFlags`
- size: `700`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, _DWORD *)`
- caller_count: `13`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x140004a60`
- `0x1400052bc`
- `0x140005fc4`
- `0x140006a14`
- `0x140008844`
- `0x140009170`
- `0x140009658`
- `0x140014448`
- `0x14001474c`
- `0x140015090`
- `0x14001a5d8`
- `0x140022258`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x140014650`
- `0x140018890`
- `0x140019544`
- `0x14001ae94`
- `0x14001c014`
- `0x14001e5e4`
- `0x14001f324`
- `0x14001f980`
- `0x140020720`
- `0x140026650`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1400189c6`
- `msvcrt!_ultow_s` at `0x1400189c6`
- `ntdll!RtlFreeHeap` at `0x140018af7`
- `ntdll!RtlFreeHeap` at `0x140018af7`

## string_xrefs

- `0x14001899c`: `BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x`
- `0x140018a11`: `BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x`
- `0x140018a92`: `BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x`

## pseudocode

```c
__int64 __fastcall BcdGetElementDataWithFlags(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v6; // rcx
  unsigned int v8; // edi
  char v9; // r15
  int v10; // eax
  unsigned int v11; // ebx
  const wchar_t *v13; // r14
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  HANDLE v17; // r12
  __int64 v18; // rcx
  int RegistryValue; // eax
  PVOID v20; // rsi
  __int64 v21; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v28; // [rsp+68h] [rbp-98h]
  _DWORD *v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Buffer[28]; // [rsp+98h] [rbp-68h] BYREF
  char v34; // [rsp+D0h] [rbp-30h] BYREF

  v31 = a1;
  v30 = a4;
  v6 = a5;
  v29 = a5;
  v27 = 5111808;
  v28 = (const wchar_t *)&v34;
  v23 = 0;
  v32 = 0;
  if ( a5 && (a4 || !*a5) )
  {
    v8 = 1;
    v9 = a1 & 1;
    LOBYTE(v6) = a1 & 1;
    v10 = BiAcquireBcdSyncMutant(v6);
    v11 = v10;
    if ( v10 < 0 )
    {
      BiLogMessage(4, L"BcdGetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v10);
      return v11;
    }
    v24 = 0;
    Handle = 0;
    P = 0;
    if ( (int)BiGetObjectIdentifier(a1, &v32) < 0 )
    {
      v13 = L"N/A";
    }
    else
    {
      BiStringFromGUID(&v32, &v27);
      v13 = v28;
    }
    v14 = BiOpenKey(a1, L"Elements", 131097, &v24);
    v11 = v14;
    if ( v14 < 0 )
    {
      BiLogMessage(
        4,
        L"BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x",
        v13,
        (unsigned int)v14);
LABEL_31:
      if ( v24 )
        BiCloseKey(v24);
      LOBYTE(v15) = v9;
      BiReleaseBcdSyncMutant(v15);
      return v11;
    }
    if ( _ultow_s(a2, Buffer, 0x16u, 16) )
    {
      v11 = -1073741823;
      goto LABEL_31;
    }
    v16 = BiOpenKey(v24, Buffer, 131097, &Handle);
    v17 = Handle;
    if ( v16 < 0 )
    {
      v18 = 2;
      if ( v16 != -1073741772 )
        v18 = 4;
      BiLogMessage(
        v18,
        L"BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x",
        v13,
        Buffer,
        v16);
      v11 = -1073741275;
LABEL_29:
      if ( v17 )
        BiCloseKey(v17);
      goto LABEL_31;
    }
    switch ( HIBYTE(a2) & 0xF )
    {
      case 1:
        goto LABEL_22;
      case 2:
      case 3:
        break;
      case 4:
        v8 = 7;
        break;
      default:
LABEL_22:
        v8 = 3;
        break;
    }
    RegistryValue = BiGetRegistryValue(Handle, L"Element", 0, v8, &P, &v23);
    v20 = P;
    v11 = RegistryValue;
    if ( RegistryValue >= 0 )
    {
      v11 = BiConvertRegistryDataToElement(v31, P, v23, a2, 0, v30, v29);
    }
    else
    {
      LODWORD(v21) = RegistryValue;
      BiLogMessage(
        4,
        L"BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x",
        v13,
        v8,
        v21);
    }
    if ( v20 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    goto LABEL_29;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140018890  push    rbp
0x140018892  push    rbx
0x140018893  push    rsi
0x140018894  push    rdi
0x140018895  push    r12
0x140018897  push    r14
0x140018899  push    r15
0x14001889b  lea     rbp, [rsp-30h]
0x1400188a0  sub     rsp, 130h
0x1400188a7  mov     rax, cs:__security_cookie
0x1400188ae  xor     rax, rsp
0x1400188b1  mov     [rbp+60h+var_40], rax
0x1400188b5  xor     r14d, r14d
0x1400188b8  mov     [rbp+60h+var_E0], rcx
0x1400188bc  mov     rsi, rcx
0x1400188bf  mov     [rsp+160h+var_E8], r9
0x1400188c4  mov     rcx, [rbp+60h+arg_20]
0x1400188cb  lea     rax, [rbp+60h+var_90]
0x1400188cf  mov     [rsp+160h+var_120], edx
0x1400188d3  xorps   xmm0, xmm0
0x1400188d6  mov     [rsp+160h+var_F0], rcx
0x1400188db  mov     r12d, edx
0x1400188de  mov     [rsp+160h+var_100], 4E0000h
0x1400188e7  mov     [rsp+160h+var_F8], rax
0x1400188ec  mov     [rsp+160h+var_11C], r14d
0x1400188f1  movups  [rbp+60h+var_D8], xmm0
0x1400188f5  test    rcx, rcx
0x1400188f8  jz      loc_140018B29
0x1400188fe  test    r9, r9
0x140018901  jnz     short loc_14001890C
0x140018903  cmp     [rcx], r14d
0x140018906  jnz     loc_140018B29
0x14001890c  mov     r15b, sil
0x14001890f  mov     edi, 1
0x140018914  and     r15b, dil
0x140018917  mov     cl, r15b
0x14001891a  call    BiAcquireBcdSyncMutant
0x14001891f  mov     ebx, eax
0x140018921  test    eax, eax
0x140018923  jns     short loc_14001893E
0x140018925  mov     r8d, eax
0x140018928  lea     rdx, aBcdgetelementd_2; "BcdGetElementDataWithFlags: Failed to a"...
0x14001892f  lea     ecx, [rdi+3]
0x140018932  call    BiLogMessage
0x140018937  mov     eax, ebx
0x140018939  jmp     loc_140018B2E
0x14001893e  lea     rdx, [rbp+60h+var_D8]
0x140018942  mov     [rsp+160h+var_118], r14
0x140018947  mov     rcx, rsi
0x14001894a  mov     [rsp+160h+Handle], r14
0x14001894f  mov     [rsp+160h+P], r14
0x140018954  call    BiGetObjectIdentifier
0x140018959  test    eax, eax
0x14001895b  js      short loc_140018972
0x14001895d  lea     rdx, [rsp+160h+var_100]
0x140018962  lea     rcx, [rbp+60h+var_D8]
0x140018966  call    BiStringFromGUID
0x14001896b  mov     r14, [rsp+160h+var_F8]
0x140018970  jmp     short loc_140018979
0x140018972  lea     r14, aNA; "N/A"
0x140018979  lea     r9, [rsp+160h+var_118]
0x14001897e  mov     r8d, 20019h
0x140018984  lea     rdx, aElements; "Elements"
0x14001898b  mov     rcx, rsi
0x14001898e  call    BiOpenKey
0x140018993  mov     ebx, eax
0x140018995  test    eax, eax
0x140018997  jns     short loc_1400189B5
0x140018999  mov     r9d, eax
0x14001899c  lea     rdx, aBcdgetelementd_0; "BcdGetElementDataWithFlags: Failed to o"...
0x1400189a3  mov     r8, r14
0x1400189a6  mov     ecx, 4
0x1400189ab  call    BiLogMessage
0x1400189b0  jmp     loc_140018B0A
0x1400189b5  mov     r9d, 10h; Radix
0x1400189bb  lea     rdx, [rbp+60h+Buffer]; Buffer
0x1400189bf  mov     ecx, r12d; Value
0x1400189c2  lea     r8d, [r9+6]; BufferCount
0x1400189c6  call    cs:__imp__ultow_s
0x1400189cc  test    eax, eax
0x1400189ce  jz      short loc_1400189DA
0x1400189d0  mov     ebx, 0C0000001h
0x1400189d5  jmp     loc_140018B0A
0x1400189da  mov     rcx, [rsp+160h+var_118]
0x1400189df  lea     r9, [rsp+160h+Handle]
0x1400189e4  mov     r8d, 20019h
0x1400189ea  lea     rdx, [rbp+60h+Buffer]
0x1400189ee  call    BiOpenKey
0x1400189f3  mov     r12, [rsp+160h+Handle]
0x1400189f8  test    eax, eax
0x1400189fa  jns     short loc_140018A2F
0x1400189fc  mov     ecx, 2
0x140018a01  mov     dword ptr [rsp+160h+var_140], eax
0x140018a05  cmp     eax, 0C0000034h
0x140018a0a  lea     r9, [rbp+60h+Buffer]
0x140018a0e  mov     r8, r14
0x140018a11  lea     rdx, aBcdgetelementd_1; "BcdGetElementDataWithFlags: Failed to o"...
0x140018a18  lea     r10d, [rcx+2]
0x140018a1c  cmovnz  ecx, r10d
0x140018a20  call    BiLogMessage
0x140018a25  mov     ebx, 0C0000225h
0x140018a2a  jmp     loc_140018AFD
0x140018a2f  mov     eax, [rsp+160h+var_120]
0x140018a33  shr     eax, 18h
0x140018a36  and     eax, 0Fh
0x140018a39  sub     eax, edi
0x140018a3b  jz      short loc_140018A4F
0x140018a3d  sub     eax, edi
0x140018a3f  jz      short loc_140018A54
0x140018a41  sub     eax, edi
0x140018a43  jz      short loc_140018A54
0x140018a45  sub     eax, edi
0x140018a47  jz      short loc_140018AA5
0x140018a49  sub     eax, edi
0x140018a4b  jz      short loc_140018A4F
0x140018a4d  sub     eax, edi
0x140018a4f  mov     edi, 3
0x140018a54  lea     rax, [rsp+160h+var_11C]
0x140018a59  mov     r9d, edi
0x140018a5c  mov     [rsp+160h+var_138], rax
0x140018a61  lea     rdx, aElement; "Element"
0x140018a68  lea     rax, [rsp+160h+P]
0x140018a6d  xor     r8d, r8d
0x140018a70  mov     rcx, r12
0x140018a73  mov     [rsp+160h+var_140], rax
0x140018a78  call    BiGetRegistryValue
0x140018a7d  mov     rsi, [rsp+160h+P]
0x140018a82  mov     ebx, eax
0x140018a84  test    eax, eax
0x140018a86  jns     short loc_140018AAC
0x140018a88  mov     r9d, edi
0x140018a8b  mov     dword ptr [rsp+160h+var_140], eax
0x140018a8f  mov     r8, r14
0x140018a92  lea     rdx, aBcdgetelementd; "BcdGetElementDataWithFlags: Failed to g"...
0x140018a99  mov     ecx, 4
0x140018a9e  call    BiLogMessage
0x140018aa3  jmp     short loc_140018AE0
0x140018aa5  mov     edi, 7
0x140018aaa  jmp     short loc_140018A54
0x140018aac  mov     rax, [rsp+160h+var_F0]
0x140018ab1  mov     rdx, rsi
0x140018ab4  mov     r9d, [rsp+160h+var_120]
0x140018ab9  mov     r8d, [rsp+160h+var_11C]
0x140018abe  mov     rcx, [rbp+60h+var_E0]
0x140018ac2  mov     [rsp+160h+var_130], rax
0x140018ac7  mov     rax, [rsp+160h+var_E8]
0x140018acc  mov     [rsp+160h+var_138], rax
0x140018ad1  mov     dword ptr [rsp+160h+var_140], 0
0x140018ad9  call    BiConvertRegistryDataToElement
0x140018ade  mov     ebx, eax
0x140018ae0  test    rsi, rsi
0x140018ae3  jz      short loc_140018AFD
0x140018ae5  mov     rcx, gs:60h
0x140018aee  mov     r8, rsi; P
0x140018af1  xor     edx, edx; Flags
0x140018af3  mov     rcx, [rcx+30h]; HeapHandle
0x140018af7  call    cs:__imp_RtlFreeHeap
0x140018afd  test    r12, r12
0x140018b00  jz      short loc_140018B0A
0x140018b02  mov     rcx, r12; Handle
0x140018b05  call    BiCloseKey
0x140018b0a  cmp     [rsp+160h+var_118], 0
0x140018b10  jz      short loc_140018B1C
0x140018b12  mov     rcx, [rsp+160h+var_118]; Handle
0x140018b17  call    BiCloseKey
0x140018b1c  mov     cl, r15b
0x140018b1f  call    BiReleaseBcdSyncMutant
0x140018b24  jmp     loc_140018937
0x140018b29  mov     eax, 0C000000Dh
0x140018b2e  mov     rcx, [rbp+60h+var_40]
0x140018b32  xor     rcx, rsp; StackCookie
0x140018b35  call    __security_check_cookie
0x140018b3a  add     rsp, 130h
0x140018b41  pop     r15
0x140018b43  pop     r14
0x140018b45  pop     r12
0x140018b47  pop     rdi
0x140018b48  pop     rsi
0x140018b49  pop     rbx
0x140018b4a  pop     rbp
0x140018b4b  retn
```
