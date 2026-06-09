# BcdSetElementDataWithFlags

- ea: `0x140018b54`
- end: `0x140018e46`
- name: `BcdSetElementDataWithFlags`
- size: `754`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `14`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x1400052bc`
- `0x1400058e4`
- `0x140005b98`
- `0x14000619c`
- `0x1400074f4`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x140008e68`
- `0x14000efc8`
- `0x14001474c`
- `0x140021990`
- `0x140021c10`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x140018b54`
- `0x140019038`
- `0x140019990`
- `0x14001ae94`
- `0x14001c014`
- `0x14001c088`
- `0x14001c6e4`
- `0x14001e5e4`
- `0x14001e730`
- `0x14001ec14`
- `0x14001f980`
- `0x14001fc5c`
- `0x1400214ec`
- `0x140026650`

## import_xrefs

- `msvcrt!_ultow_s` at `0x140018ca5`
- `msvcrt!_ultow_s` at `0x140018ca5`
- `ntdll!RtlFreeHeap` at `0x140018dc1`
- `ntdll!RtlFreeHeap` at `0x140018dc1`

## string_xrefs

- `0x140018c7b`: `Failed to open key for object's elements. Status: %x`
- `0x140018cf1`: `Failed to open key for element %s. Status: %x`
- `0x140018d92`: `Failed to set registry data for element %s. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdSetElementDataWithFlags(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  unsigned int v6; // ebx
  HANDLE v8; // r15
  HANDLE v9; // r14
  unsigned int v10; // esi
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edi
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  errno_t v17; // eax
  int v18; // eax
  int v19; // eax
  PVOID v20; // r13
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // eax
  char v25; // [rsp+30h] [rbp-61h] BYREF
  char v26; // [rsp+31h] [rbp-60h]
  unsigned int v27; // [rsp+34h] [rbp-5Dh]
  int v28; // [rsp+38h] [rbp-59h] BYREF
  HANDLE v29; // [rsp+40h] [rbp-51h] BYREF
  int v30; // [rsp+48h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-41h] BYREF
  __int64 v32; // [rsp+58h] [rbp-39h]
  PVOID P; // [rsp+60h] [rbp-31h] BYREF
  wchar_t Buffer[24]; // [rsp+68h] [rbp-29h] BYREF

  v32 = a4;
  v27 = a3;
  v6 = a2;
  v30 = a2;
  v28 = 0;
  if ( !a4 && a5 )
    return 3221225485LL;
  v29 = 0;
  v8 = 0;
  v25 = 0;
  v9 = 0;
  Handle = 0;
  P = 0;
  if ( !a5 )
  {
    BiDeleteElement(a1, a2, 1);
    return 0;
  }
  BiLogMessage(2, L"Setting element %08x", (unsigned int)a2);
  v10 = 1;
  LOBYTE(v11) = a1 & 1;
  v26 = a1 & 1;
  v12 = BiAcquireBcdSyncMutant(v11);
  v13 = v12;
  if ( v12 >= 0 )
  {
    if ( (v27 & 0x80u) == 0 )
    {
      v14 = BiFilterDoOperation(1, a1, v6, v32, a5);
      v13 = v14;
      if ( v14 < 0 )
      {
        BiLogMessage(4, L"Failed filtering for element %08x. Status: 0x%x", v6, (unsigned int)v14);
        goto LABEL_29;
      }
    }
    v16 = BiOpenKey(a1, L"Elements", 131101, &v29);
    v13 = v16;
    if ( v16 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for object's elements. Status: %x", (unsigned int)v16);
      v8 = v29;
      goto LABEL_29;
    }
    v17 = _ultow_s(v6, Buffer, 0x16u, 16);
    v8 = v29;
    if ( v17 )
    {
      v13 = -1073741823;
LABEL_33:
      if ( v8 )
        BiCloseKey(v8);
      if ( v13 >= 0 )
      {
        if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v30) )
          BiSetFirmwareModifiedFromObject(a1);
      }
      LOBYTE(v15) = v26;
      BiReleaseBcdSyncMutant(v15);
      return (unsigned int)v13;
    }
    v18 = BiCreateKey(v29, Buffer, 65538, 1, &Handle, &v25);
    v13 = v18;
    if ( v18 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for element %s. Status: %x", Buffer, (unsigned int)v18);
      v9 = Handle;
LABEL_29:
      if ( v25 )
      {
        BiDeleteKey(v9);
        v9 = 0;
      }
LABEL_31:
      if ( v9 )
        BiCloseKey(v9);
      goto LABEL_33;
    }
    v19 = BiConvertElementToRegistryData(v6, v32, a5, v27, &P, &v28);
    v9 = Handle;
    v13 = v19;
    v20 = P;
    if ( v19 < 0 )
    {
      BiLogMessage(4, L"Failed to convert data for element %s. Status: %x", Buffer, (unsigned int)v19);
      goto LABEL_26;
    }
    v21 = (HIBYTE(v6) & 0xF) - 1;
    if ( !v21 )
      goto LABEL_23;
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 != 1 )
        {
LABEL_23:
          v10 = 3;
          goto LABEL_24;
        }
        v10 = 7;
      }
    }
LABEL_24:
    v24 = BiSetRegistryValue(Handle, L"Element", 0, v10, P, v28);
    v13 = v24;
    if ( v24 < 0 )
      BiLogMessage(4, L"Failed to set registry data for element %s. Status: %x", Buffer, (unsigned int)v24);
LABEL_26:
    if ( v20 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    if ( v13 >= 0 )
      goto LABEL_31;
    goto LABEL_29;
  }
  BiLogMessage(4, L"BcdSetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140018b54  push    rbp
0x140018b56  push    rbx
0x140018b57  push    rsi
0x140018b58  push    rdi
0x140018b59  push    r12
0x140018b5b  push    r13
0x140018b5d  push    r14
0x140018b5f  push    r15
0x140018b61  lea     rbp, [rsp-17h]
0x140018b66  sub     rsp, 0A8h
0x140018b6d  mov     rax, cs:__security_cookie
0x140018b74  xor     rax, rsp
0x140018b77  mov     [rbp+4Fh+var_48], rax
0x140018b7b  mov     r13d, [rbp+4Fh+arg_20]
0x140018b7f  mov     r12, rcx
0x140018b82  xor     ecx, ecx
0x140018b84  mov     [rbp+4Fh+var_88], r9
0x140018b88  mov     [rbp+4Fh+var_AC], r8d
0x140018b8c  mov     ebx, edx
0x140018b8e  mov     [rbp+4Fh+var_98], edx
0x140018b91  mov     [rbp+4Fh+var_A8], ecx
0x140018b94  test    r9, r9
0x140018b97  jnz     short loc_140018BA8
0x140018b99  test    r13d, r13d
0x140018b9c  jz      short loc_140018BA8
0x140018b9e  mov     eax, 0C000000Dh
0x140018ba3  jmp     loc_140018E1C
0x140018ba8  mov     [rbp+4Fh+var_A0], rcx
0x140018bac  mov     r15, rcx
0x140018baf  mov     [rbp+4Fh+var_B0], cl
0x140018bb2  mov     r14, rcx
0x140018bb5  mov     [rbp+4Fh+Handle], rcx
0x140018bb9  mov     [rbp+4Fh+P], rcx
0x140018bbd  test    r13d, r13d
0x140018bc0  jnz     short loc_140018BD5
0x140018bc2  lea     r8d, [r13+1]
0x140018bc6  mov     rcx, r12
0x140018bc9  call    BiDeleteElement
0x140018bce  xor     eax, eax
0x140018bd0  jmp     loc_140018E1C
0x140018bd5  mov     r8d, ebx
0x140018bd8  lea     rdx, aSettingElement; "Setting element %08x"
0x140018bdf  mov     ecx, 2
0x140018be4  call    BiLogMessage
0x140018be9  mov     al, r12b
0x140018bec  mov     esi, 1
0x140018bf1  and     al, sil
0x140018bf4  mov     cl, al
0x140018bf6  mov     [rbp+4Fh+var_AF], al
0x140018bf9  call    BiAcquireBcdSyncMutant
0x140018bfe  mov     edi, eax
0x140018c00  test    eax, eax
0x140018c02  jns     short loc_140018C1B
0x140018c04  mov     r8d, eax
0x140018c07  lea     rdx, aBcdsetelementd; "BcdSetElementDataWithFlags: Failed to a"...
0x140018c0e  lea     ecx, [rsi+3]
0x140018c11  call    BiLogMessage
0x140018c16  jmp     loc_140018E1A
0x140018c1b  test    byte ptr [rbp+4Fh+var_AC], 80h
0x140018c1f  jnz     short loc_140018C59
0x140018c21  mov     r9, [rbp+4Fh+var_88]
0x140018c25  mov     r8d, ebx
0x140018c28  mov     rdx, r12
0x140018c2b  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x140018c30  mov     ecx, esi
0x140018c32  call    BiFilterDoOperation
0x140018c37  mov     edi, eax
0x140018c39  test    eax, eax
0x140018c3b  jns     short loc_140018C59
0x140018c3d  mov     r9d, eax
0x140018c40  lea     rdx, aFailedFilterin; "Failed filtering for element %08x. Stat"...
0x140018c47  mov     r8d, ebx
0x140018c4a  mov     ecx, 4
0x140018c4f  call    BiLogMessage
0x140018c54  jmp     loc_140018DCB
0x140018c59  lea     r9, [rbp+4Fh+var_A0]
0x140018c5d  mov     r8d, 2001Dh
0x140018c63  lea     rdx, aElements; "Elements"
0x140018c6a  mov     rcx, r12
0x140018c6d  call    BiOpenKey
0x140018c72  mov     edi, eax
0x140018c74  test    eax, eax
0x140018c76  jns     short loc_140018C95
0x140018c78  mov     r8d, eax
0x140018c7b  lea     rdx, aFailedToOpenKe_0; "Failed to open key for object's element"...
0x140018c82  mov     ecx, 4
0x140018c87  call    BiLogMessage
0x140018c8c  mov     r15, [rbp+4Fh+var_A0]
0x140018c90  jmp     loc_140018DCB
0x140018c95  mov     r9d, 10h; Radix
0x140018c9b  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x140018c9f  mov     ecx, ebx; Value
0x140018ca1  lea     r8d, [r9+6]; BufferCount
0x140018ca5  call    cs:__imp__ultow_s
0x140018cab  mov     r15, [rbp+4Fh+var_A0]
0x140018caf  test    eax, eax
0x140018cb1  jz      short loc_140018CBD
0x140018cb3  mov     edi, 0C0000001h
0x140018cb8  jmp     loc_140018DE9
0x140018cbd  lea     rax, [rbp+4Fh+var_B0]
0x140018cc1  mov     r9d, esi
0x140018cc4  mov     [rsp+0E0h+var_B8], rax
0x140018cc9  lea     rdx, [rbp+4Fh+Buffer]
0x140018ccd  lea     rax, [rbp+4Fh+Handle]
0x140018cd1  mov     r8d, 10002h
0x140018cd7  mov     rcx, r15
0x140018cda  mov     [rsp+0E0h+var_C0], rax
0x140018cdf  call    BiCreateKey
0x140018ce4  mov     edi, eax
0x140018ce6  test    eax, eax
0x140018ce8  jns     short loc_140018D0B
0x140018cea  mov     r9d, eax
0x140018ced  lea     r8, [rbp+4Fh+Buffer]
0x140018cf1  lea     rdx, aFailedToOpenKe_1; "Failed to open key for element %s. Stat"...
0x140018cf8  mov     ecx, 4
0x140018cfd  call    BiLogMessage
0x140018d02  mov     r14, [rbp+4Fh+Handle]
0x140018d06  jmp     loc_140018DCB
0x140018d0b  mov     r9d, [rbp+4Fh+var_AC]
0x140018d0f  lea     rax, [rbp+4Fh+var_A8]
0x140018d13  mov     rdx, [rbp+4Fh+var_88]
0x140018d17  mov     r8d, r13d
0x140018d1a  mov     [rsp+0E0h+var_B8], rax
0x140018d1f  mov     ecx, ebx
0x140018d21  lea     rax, [rbp+4Fh+P]
0x140018d25  mov     [rsp+0E0h+var_C0], rax
0x140018d2a  call    BiConvertElementToRegistryData
0x140018d2f  mov     r14, [rbp+4Fh+Handle]
0x140018d33  mov     edi, eax
0x140018d35  mov     r13, [rbp+4Fh+P]
0x140018d39  test    eax, eax
0x140018d3b  jns     short loc_140018D46
0x140018d3d  lea     rdx, aFailedToConver_0; "Failed to convert data for element %s. "...
0x140018d44  jmp     short loc_140018D99
0x140018d46  shr     ebx, 18h
0x140018d49  and     ebx, 0Fh
0x140018d4c  sub     ebx, esi
0x140018d4e  jz      short loc_140018D66
0x140018d50  sub     ebx, esi
0x140018d52  jz      short loc_140018D6B
0x140018d54  sub     ebx, esi
0x140018d56  jz      short loc_140018D6B
0x140018d58  sub     ebx, esi
0x140018d5a  jz      loc_140018E3C
0x140018d60  sub     ebx, esi
0x140018d62  jz      short loc_140018D66
0x140018d64  sub     ebx, esi
0x140018d66  mov     esi, 3
0x140018d6b  mov     eax, [rbp+4Fh+var_A8]
0x140018d6e  lea     rdx, aElement; "Element"
0x140018d75  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140018d79  mov     r9d, esi
0x140018d7c  xor     r8d, r8d
0x140018d7f  mov     [rsp+0E0h+var_C0], r13
0x140018d84  mov     rcx, r14
0x140018d87  call    BiSetRegistryValue
0x140018d8c  mov     edi, eax
0x140018d8e  test    eax, eax
0x140018d90  jns     short loc_140018DAA
0x140018d92  lea     rdx, aFailedToSetReg; "Failed to set registry data for element"...
0x140018d99  mov     r9d, eax
0x140018d9c  lea     r8, [rbp+4Fh+Buffer]
0x140018da0  mov     ecx, 4
0x140018da5  call    BiLogMessage
0x140018daa  test    r13, r13
0x140018dad  jz      short loc_140018DC7
0x140018daf  mov     rcx, gs:60h
0x140018db8  mov     r8, r13; P
0x140018dbb  xor     edx, edx; Flags
0x140018dbd  mov     rcx, [rcx+30h]; HeapHandle
0x140018dc1  call    cs:__imp_RtlFreeHeap
0x140018dc7  test    edi, edi
0x140018dc9  jns     short loc_140018DDC
0x140018dcb  cmp     [rbp+4Fh+var_B0], 0
0x140018dcf  jz      short loc_140018DDC
0x140018dd1  mov     rcx, r14
0x140018dd4  call    BiDeleteKey
0x140018dd9  xor     r14d, r14d
0x140018ddc  test    r14, r14
0x140018ddf  jz      short loc_140018DE9
0x140018de1  mov     rcx, r14; Handle
0x140018de4  call    BiCloseKey
0x140018de9  test    r15, r15
0x140018dec  jz      short loc_140018DF6
0x140018dee  mov     rcx, r15; Handle
0x140018df1  call    BiCloseKey
0x140018df6  test    edi, edi
0x140018df8  js      short loc_140018E12
0x140018dfa  lea     rdx, [rbp+4Fh+var_98]
0x140018dfe  mov     rcx, r12
0x140018e01  call    BiIsLinkedToFirmwareVariable
0x140018e06  test    al, al
0x140018e08  jz      short loc_140018E12
0x140018e0a  mov     rcx, r12
0x140018e0d  call    BiSetFirmwareModifiedFromObject
0x140018e12  mov     cl, [rbp+4Fh+var_AF]
0x140018e15  call    BiReleaseBcdSyncMutant
0x140018e1a  mov     eax, edi
0x140018e1c  mov     rcx, [rbp+4Fh+var_48]
0x140018e20  xor     rcx, rsp; StackCookie
0x140018e23  call    __security_check_cookie
0x140018e28  add     rsp, 0A8h
0x140018e2f  pop     r15
0x140018e31  pop     r14
0x140018e33  pop     r13
0x140018e35  pop     r12
0x140018e37  pop     rdi
0x140018e38  pop     rsi
0x140018e39  pop     rbx
0x140018e3a  pop     rbp
0x140018e3b  retn
0x140018e3c  mov     esi, 7
0x140018e41  jmp     loc_140018D6B
```
