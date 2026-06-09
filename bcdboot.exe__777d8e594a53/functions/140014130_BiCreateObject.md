# BiCreateObject

- ea: `0x140014130`
- end: `0x140014441`
- name: `BiCreateObject`
- size: `785`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned int *, char, _QWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001474c`
- `0x140021c10`
- `0x140021f58`

## callees

- `0x1400133e4`
- `0x140014130`
- `0x14001e5e4`
- `0x14001e730`
- `0x14001f980`
- `0x14001fc5c`
- `0x140020720`
- `0x1400209d0`
- `0x140026650`

## pseudocode

```c
__int64 __fastcall BiCreateObject(__int64 a1, __int128 *a2, unsigned int *a3, char a4, _QWORD *a5)
{
  unsigned int *v5; // r15
  void *v7; // r14
  __int64 v9; // r9
  __int64 v11; // r8
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // eax
  bool v16; // zf
  __int64 result; // rax
  int v18; // eax
  HANDLE v19; // rsi
  int v20; // ebx
  int v21; // eax
  HANDLE v22; // rdi
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  bool v27; // [rsp+30h] [rbp-81h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-79h] BYREF
  void *v29; // [rsp+40h] [rbp-71h] BYREF
  __int64 v30; // [rsp+48h] [rbp-69h] BYREF
  const WCHAR *v31; // [rsp+50h] [rbp-61h]
  HANDLE v32; // [rsp+58h] [rbp-59h] BYREF
  __int128 v33; // [rsp+60h] [rbp-51h] BYREF
  char v34; // [rsp+70h] [rbp-41h] BYREF

  v5 = a3 + 1;
  v30 = 5111808;
  v7 = 0;
  v32 = 0;
  *a5 = 0;
  v9 = a3[1];
  v11 = *a3;
  Handle = 0;
  v29 = 0;
  v31 = (const WCHAR *)&v34;
  v33 = 0;
  BiLogMessage(2, L"Creating object. Version: %d. Type: 0x%08x", v11, v9);
  if ( !a3 )
    return (unsigned int)-1073741637;
  if ( !*a3 )
    return (unsigned int)-1073741637;
  v13 = *v5;
  v14 = *v5 >> 28;
  if ( !v14 )
    return (unsigned int)-1073741637;
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 != 1 )
      goto LABEL_10;
    if ( (v13 & 0xF00000) == 0 )
      return (unsigned int)-1073741637;
    if ( (v13 & 0xF00000) != 0x200000 )
      goto LABEL_10;
    v16 = (v13 & 0xFFFFF) == 0;
  }
  else
  {
    v24 = v13 & 0xFFFFF;
    if ( (v13 & 0xFFFFF) == 0 )
      return (unsigned int)-1073741637;
    v25 = (v13 >> 20) & 0xF;
    if ( !v25 )
      return (unsigned int)-1073741637;
    if ( v25 != 1 )
      goto LABEL_10;
    v26 = v24 - 1;
    if ( !v26 )
    {
      if ( a2
        && *(_QWORD *)a2 == *(_QWORD *)&GUID_FIRMWARE_BOOTMGR.Data1
        && *((_QWORD *)a2 + 1) == *(_QWORD *)GUID_FIRMWARE_BOOTMGR.Data4 )
      {
        goto LABEL_38;
      }
      return (unsigned int)-1073741637;
    }
    if ( v26 != 1048574 )
    {
LABEL_10:
      if ( !a2 )
      {
        BiLogMessage(2, L"Generating object GUID.");
        result = BiGenerateObjectGuid(a1, &v33);
        if ( (int)result < 0 )
          return result;
        a2 = &v33;
        goto LABEL_13;
      }
LABEL_38:
      if ( *(_QWORD *)a2 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1
        && *((_QWORD *)a2 + 1) == *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4
        || *(_QWORD *)a2 == *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1
        && *((_QWORD *)a2 + 1) == *(_QWORD *)GUID_DEFAULT_BOOT_ENTRY.Data4 )
      {
        return 3221225523LL;
      }
LABEL_13:
      BiStringFromGUID(a2, &v30);
      BiLogMessage(2, L"Object GUID: %s", v31);
      v18 = BiOpenKey(a1, L"Objects", 4, &v32);
      v19 = v32;
      v20 = v18;
      if ( v18 >= 0 )
      {
        v21 = BiCreateKey((unsigned __int64)v32, v31, 0xF003Fu, 0, &Handle, &v27);
        v22 = Handle;
        v20 = v21;
        if ( v21 < 0 )
          goto LABEL_22;
        Handle = 0;
        v20 = BiCreateKey((unsigned __int64)v22, L"Description", 0x20019u, 1u, &Handle, &v27);
        if ( v20 >= 0 )
        {
          BiCloseKey(Handle);
          v20 = BiSetRegistryValue(v22, L"Type", L"Description", 4, v5, 4);
          if ( v20 >= 0 )
          {
            v23 = BiCreateKey((unsigned __int64)v22, L"Elements", 0x20019u, 0, &v29, &v27);
            v7 = v29;
            v20 = v23;
            if ( v23 >= 0 )
            {
              *a5 = v22;
              v20 = 0;
            }
          }
        }
        if ( v7 )
          BiCloseKey(v7);
        if ( v20 < 0 )
        {
LABEL_22:
          if ( v22 )
            BiCloseKey(v22);
        }
      }
      if ( v19 )
        BiCloseKey(v19);
      return (unsigned int)v20;
    }
    v16 = (a4 & 1) == 0;
  }
  if ( !v16 )
    goto LABEL_10;
  return (unsigned int)-1073741637;
}

```

## disassembly

```asm
0x140014130  mov     [rsp-8+arg_18], rbx
0x140014135  push    rbp
0x140014136  push    rsi
0x140014137  push    rdi
0x140014138  push    r12
0x14001413a  push    r13
0x14001413c  push    r14
0x14001413e  push    r15
0x140014140  lea     rbp, [rsp-1Fh]
0x140014145  sub     rsp, 0D0h
0x14001414c  mov     rax, cs:__security_cookie
0x140014153  xor     rax, rsp
0x140014156  mov     [rbp+4Fh+var_40], rax
0x14001415a  mov     r13, [rbp+4Fh+arg_20]
0x14001415e  lea     r15, [r8+4]
0x140014162  mov     r12, rcx
0x140014165  mov     [rbp+4Fh+var_B8], 4E0000h
0x14001416d  xor     ecx, ecx
0x14001416f  lea     rax, [rbp+4Fh+var_90]
0x140014173  mov     r14d, ecx
0x140014176  mov     [rbp+4Fh+var_A8], rcx
0x14001417a  mov     [r13+0], rcx
0x14001417e  mov     esi, r9d
0x140014181  mov     r9d, [r15]
0x140014184  mov     rdi, r8
0x140014187  mov     r8d, [r8]
0x14001418a  mov     rbx, rdx
0x14001418d  xorps   xmm0, xmm0
0x140014190  mov     [rbp+4Fh+Handle], rcx
0x140014194  mov     [rbp+4Fh+var_C0], rcx
0x140014198  lea     rdx, aCreatingObject; "Creating object. Version: %d. Type: 0x%"...
0x14001419f  lea     ecx, [r14+2]
0x1400141a3  mov     [rbp+4Fh+var_B0], rax
0x1400141a7  movups  [rbp+4Fh+var_A0], xmm0
0x1400141ab  call    BiLogMessage
0x1400141b0  test    rdi, rdi
0x1400141b3  jz      loc_1400143D2
0x1400141b9  cmp     [rdi], r14d
0x1400141bc  jz      loc_1400143D2
0x1400141c2  mov     ecx, [r15]
0x1400141c5  mov     eax, ecx
0x1400141c7  shr     eax, 1Ch
0x1400141ca  test    eax, eax
0x1400141cc  jz      loc_1400143D2
0x1400141d2  sub     eax, 1
0x1400141d5  jz      loc_140014383
0x1400141db  cmp     eax, 1
0x1400141de  jnz     short loc_140014200
0x1400141e0  mov     eax, ecx
0x1400141e2  and     eax, 0F00000h
0x1400141e7  jz      loc_1400143D2
0x1400141ed  cmp     eax, 200000h
0x1400141f2  jnz     short loc_140014200
0x1400141f4  test    ecx, 0FFFFFh
0x1400141fa  jz      loc_1400143D2
0x140014200  test    rbx, rbx
0x140014203  jnz     loc_140014400
0x140014209  lea     rdx, aGeneratingObje; "Generating object GUID."
0x140014210  lea     ecx, [rbx+2]
0x140014213  call    BiLogMessage
0x140014218  lea     rdx, [rbp+4Fh+var_A0]
0x14001421c  mov     rcx, r12
0x14001421f  call    BiGenerateObjectGuid
0x140014224  test    eax, eax
0x140014226  js      loc_1400143D9
0x14001422c  lea     rbx, [rbp+4Fh+var_A0]
0x140014230  lea     rdx, [rbp+4Fh+var_B8]
0x140014234  mov     rcx, rbx
0x140014237  call    BiStringFromGUID
0x14001423c  mov     r8, [rbp+4Fh+var_B0]
0x140014240  lea     rdx, aObjectGuidS; "Object GUID: %s"
0x140014247  mov     ecx, 2
0x14001424c  call    BiLogMessage
0x140014251  lea     r9, [rbp+4Fh+var_A8]
0x140014255  mov     r8d, 4
0x14001425b  lea     rdx, aObjects; "Objects"
0x140014262  mov     rcx, r12
0x140014265  call    BiOpenKey
0x14001426a  mov     rsi, [rbp+4Fh+var_A8]
0x14001426e  mov     ebx, eax
0x140014270  test    eax, eax
0x140014272  js      loc_140014374
0x140014278  mov     rdx, [rbp+4Fh+var_B0]
0x14001427c  lea     rax, [rsp+100h+var_D0]
0x140014281  mov     [rsp+100h+var_D8], rax
0x140014286  xor     r9d, r9d
0x140014289  lea     rax, [rbp+4Fh+Handle]
0x14001428d  mov     r8d, 0F003Fh
0x140014293  mov     rcx, rsi
0x140014296  mov     [rsp+100h+var_E0], rax
0x14001429b  call    BiCreateKey
0x1400142a0  mov     rdi, [rbp+4Fh+Handle]
0x1400142a4  mov     ebx, eax
0x1400142a6  test    eax, eax
0x1400142a8  js      loc_140014367
0x1400142ae  lea     rax, [rsp+100h+var_D0]
0x1400142b3  mov     [rbp+4Fh+Handle], r14
0x1400142b7  mov     [rsp+100h+var_D8], rax
0x1400142bc  lea     rdx, aDescription; "Description"
0x1400142c3  lea     rax, [rbp+4Fh+Handle]
0x1400142c7  mov     r12d, 20019h
0x1400142cd  mov     r9d, 1
0x1400142d3  mov     [rsp+100h+var_E0], rax
0x1400142d8  mov     r8d, r12d
0x1400142db  mov     rcx, rdi
0x1400142de  call    BiCreateKey
0x1400142e3  mov     ebx, eax
0x1400142e5  test    eax, eax
0x1400142e7  js      short loc_140014356
0x1400142e9  mov     rcx, [rbp+4Fh+Handle]; Handle
0x1400142ed  call    BiCloseKey
0x1400142f2  mov     r9d, 4
0x1400142f8  lea     r8, aDescription; "Description"
0x1400142ff  mov     dword ptr [rsp+100h+var_D8], r9d
0x140014304  lea     rdx, aType; "Type"
0x14001430b  mov     rcx, rdi
0x14001430e  mov     [rsp+100h+var_E0], r15
0x140014313  call    BiSetRegistryValue
0x140014318  mov     ebx, eax
0x14001431a  test    eax, eax
0x14001431c  js      short loc_140014356
0x14001431e  lea     rax, [rsp+100h+var_D0]
0x140014323  xor     r9d, r9d
0x140014326  mov     [rsp+100h+var_D8], rax
0x14001432b  lea     rdx, aElements; "Elements"
0x140014332  lea     rax, [rbp+4Fh+var_C0]
0x140014336  mov     r8d, r12d
0x140014339  mov     rcx, rdi
0x14001433c  mov     [rsp+100h+var_E0], rax
0x140014341  call    BiCreateKey
0x140014346  mov     r14, [rbp+4Fh+var_C0]
0x14001434a  mov     ebx, eax
0x14001434c  test    eax, eax
0x14001434e  js      short loc_140014356
0x140014350  mov     [r13+0], rdi
0x140014354  xor     ebx, ebx
0x140014356  test    r14, r14
0x140014359  jz      short loc_140014363
0x14001435b  mov     rcx, r14; Handle
0x14001435e  call    BiCloseKey
0x140014363  test    ebx, ebx
0x140014365  jns     short loc_140014374
0x140014367  test    rdi, rdi
0x14001436a  jz      short loc_140014374
0x14001436c  mov     rcx, rdi; Handle
0x14001436f  call    BiCloseKey
0x140014374  test    rsi, rsi
0x140014377  jz      short loc_1400143D7
0x140014379  mov     rcx, rsi; Handle
0x14001437c  call    BiCloseKey
0x140014381  jmp     short loc_1400143D7
0x140014383  mov     eax, ecx
0x140014385  and     eax, 0FFFFFh
0x14001438a  jz      short loc_1400143D2
0x14001438c  shr     ecx, 14h
0x14001438f  and     ecx, 0Fh
0x140014392  jz      short loc_1400143D2
0x140014394  cmp     ecx, 1
0x140014397  jnz     loc_140014200
0x14001439d  sub     eax, ecx
0x14001439f  jz      short loc_1400143B4
0x1400143a1  cmp     eax, 0FFFFEh
0x1400143a6  jnz     loc_140014200
0x1400143ac  test    cl, sil
0x1400143af  jmp     loc_1400141FA
0x1400143b4  test    rbx, rbx
0x1400143b7  jz      short loc_1400143D2
0x1400143b9  mov     rax, [rbx]
0x1400143bc  cmp     rax, qword ptr cs:GUID_FIRMWARE_BOOTMGR.Data1
0x1400143c3  jnz     short loc_1400143D2
0x1400143c5  mov     rax, [rbx+8]
0x1400143c9  cmp     rax, qword ptr cs:GUID_FIRMWARE_BOOTMGR.Data4
0x1400143d0  jz      short loc_140014400
0x1400143d2  mov     ebx, 0C00000BBh
0x1400143d7  mov     eax, ebx
0x1400143d9  mov     rcx, [rbp+4Fh+var_40]
0x1400143dd  xor     rcx, rsp; StackCookie
0x1400143e0  call    __security_check_cookie
0x1400143e5  mov     rbx, [rsp+100h+arg_18]
0x1400143ed  add     rsp, 0D0h
0x1400143f4  pop     r15
0x1400143f6  pop     r14
0x1400143f8  pop     r13
0x1400143fa  pop     r12
0x1400143fc  pop     rdi
0x1400143fd  pop     rsi
0x1400143fe  pop     rbp
0x1400143ff  retn
0x140014400  mov     rax, [rbx]
0x140014403  cmp     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x14001440a  jnz     short loc_140014419
0x14001440c  mov     rax, [rbx+8]
0x140014410  cmp     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x140014417  jz      short loc_14001443A
0x140014419  mov     rax, [rbx]
0x14001441c  cmp     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data1
0x140014423  jnz     loc_140014230
0x140014429  mov     rax, [rbx+8]
0x14001442d  cmp     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data4
0x140014434  jnz     loc_140014230
0x14001443a  mov     eax, 0C0000033h
0x14001443f  jmp     short loc_1400143D9
```
