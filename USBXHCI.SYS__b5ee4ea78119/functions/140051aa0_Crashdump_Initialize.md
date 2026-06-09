# Crashdump_Initialize

- ea: `0x140051aa0`
- end: `0x140051d96`
- name: `Crashdump_Initialize`
- size: `758`
- prototype: `__int64 __fastcall(PVOID Address)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140051aa0`
- `0x140051fcc`
- `0x1400521e0`
- `0x140052e78`
- `0x140052fb8`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140051acb`
- `ntoskrnl!DbgPrintEx` at `0x140051b3a`
- `ntoskrnl!DbgPrintEx` at `0x140051b7f`
- `ntoskrnl!DbgPrintEx` at `0x140051ba7`
- `ntoskrnl!DbgPrintEx` at `0x140051bf9`
- `ntoskrnl!DbgPrintEx` at `0x140051c51`
- `ntoskrnl!DbgPrintEx` at `0x140051ce3`
- `ntoskrnl!DbgPrintEx` at `0x140051d0d`
- `ntoskrnl!DbgPrintEx` at `0x140051d78`
- `ntoskrnl!DbgPrintEx` at `0x140051acb`
- `ntoskrnl!DbgPrintEx` at `0x140051b3a`
- `ntoskrnl!DbgPrintEx` at `0x140051b7f`
- `ntoskrnl!DbgPrintEx` at `0x140051ba7`
- `ntoskrnl!DbgPrintEx` at `0x140051bf9`
- `ntoskrnl!DbgPrintEx` at `0x140051c51`
- `ntoskrnl!DbgPrintEx` at `0x140051ce3`
- `ntoskrnl!DbgPrintEx` at `0x140051d0d`
- `ntoskrnl!DbgPrintEx` at `0x140051d78`

## string_xrefs

- `0x140051c28`: `XHCIDUMP: xHC is not ready, cannot continue.\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Initialize(_DWORD *Address)
{
  int v2; // ebp
  const char *v3; // r9
  __int128 v4; // xmm0
  int v5; // edi
  int v6; // ebx
  bool v7; // zf
  int v8; // eax
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  __int64 **v16; // rbx
  int v17; // eax
  int v18; // eax
  _OWORD v20[4]; // [rsp+40h] [rbp-48h]

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Initialize: Begin\n");
  v2 = 2;
  v3 = "HS";
  v4 = *(_OWORD *)(Address + 2);
  v5 = HIBYTE(**(_DWORD **)(*(_QWORD *)Address + 24LL));
  v6 = HIWORD(**(_DWORD **)(*(_QWORD *)Address + 24LL));
  v7 = Address[131] == 2;
  *((_BYTE *)Address + 627) = HIBYTE(**(_DWORD **)(*(_QWORD *)Address + 24LL));
  if ( !v7 )
    v3 = "SS";
  *((_BYTE *)Address + 628) = v6;
  *((_BYTE *)Address + 624) = 0;
  v8 = Address[136];
  v20[0] = v4;
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Device speed: %s, RootHub port #: %u\n", v3, v8);
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: xHCI version: 0x%x.0x%x, ContextSize: %u, ScratchpadBuffers: %u, DeviceSlots: %u\n",
    v5,
    (unsigned __int8)v6,
    (*(_DWORD *)(*(_QWORD *)Address + 104LL) >> 2) & 1,
    Address[7],
    Address[6]);
  v9 = 0;
  do
  {
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Device Flag[%d]:  0x%I64X\n", v9, *((_QWORD *)v20 + v9));
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (unsigned int)v9 < 2 );
  v10 = Address[146];
  if ( v10 == 2 )
  {
    Address[146] = 3;
  }
  else if ( ((v10 - 1) & 0xFFFFFFFB) == 0 )
  {
    *((_BYTE *)Address + 626) = 1;
    v11 = Crashdump_InitializeWithoutControllerReset((char *)Address);
    if ( v11 < 0 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_InitializeWithoutControllerReset failed with error 0x%X\n", v11);
      v12 = Crashdump_InitializeWithControllerReset((__int64)Address);
      v13 = v12;
      if ( v12 < 0 )
      {
LABEL_25:
        DbgPrintEx(
          0x93u,
          1u,
          "XHCIDUMP: Crashdump_InitializeWithControllerReset failed with error 0x%X\n",
          (unsigned int)v12);
        goto LABEL_26;
      }
    }
  }
  v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)Address + 32LL) + 4LL);
  if ( (v14 & 0x800) != 0 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: xHC is not ready, cannot continue.\n");
LABEL_16:
    v13 = -1073741823;
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Register_VerifyRegisterState failed with error 0x%X\n", 3221225473LL);
    goto LABEL_26;
  }
  if ( (v14 & 4) != 0 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Host System Error bit is set, cannot continue.\n");
    goto LABEL_16;
  }
  if ( (v14 & 0x1000) != 0 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: xHC is in an error state, cannot continue.\n");
    goto LABEL_16;
  }
  v15 = Address[146];
  if ( !v15 || (v13 = 0, v15 == 3) )
  {
    Crashdump_Register_LogRHPortInfo(Address, (unsigned int)Address[136]);
    if ( Address[146] == 3 )
    {
      v16 = (__int64 **)*((_QWORD *)Address + 62);
      if ( *v16 != (__int64 *)v16 )
      {
        do
        {
          memset(v16[2], 0, *((unsigned int *)v16 + 10));
          v16 = (__int64 **)*v16;
        }
        while ( *v16 != *((__int64 **)Address + 62) );
      }
      v17 = Crashdump_Register_BiosHandoff((__int64)Address);
      if ( v17 < 0 )
        DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_Register_BiosHandoff failed with error 0x%X\n", v17);
    }
    v12 = Crashdump_InitializeWithControllerReset((__int64)Address);
    v13 = v12;
    if ( v12 < 0 )
      goto LABEL_25;
  }
LABEL_26:
  v18 = Address[146];
  *((_BYTE *)Address + 625) = 0;
  if ( v18 == 1 )
  {
    Address[146] = 2;
    goto LABEL_33;
  }
  if ( v18 != 5 )
  {
    v2 = v18;
LABEL_33:
    if ( v2 == 3 )
      Address[146] = 4;
    goto LABEL_35;
  }
  Address[146] = 2;
  if ( (v20[0] & 2) == 0 && !*((_BYTE *)Address + 624) )
    *((_BYTE *)Address + 625) = 1;
LABEL_35:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Initialize: End 0x%X\n", v13);
  return v13;
}

```

## disassembly

```asm
0x140051aa0  push    rbx
0x140051aa2  push    rbp
0x140051aa3  push    rsi
0x140051aa4  push    rdi
0x140051aa5  push    r13
0x140051aa7  push    r14
0x140051aa9  push    r15
0x140051aab  sub     rsp, 50h
0x140051aaf  mov     rsi, rcx
0x140051ab2  lea     r8, aXhcidumpCrashd_40; "XHCIDUMP: Crashdump_Initialize: Begin\n"
0x140051ab9  mov     r13d, 3
0x140051abf  mov     r15d, 93h
0x140051ac5  mov     edx, r13d; Level
0x140051ac8  mov     ecx, r15d; ComponentId
0x140051acb  call    cs:__imp_DbgPrintEx
0x140051ad2  nop     dword ptr [rax+rax+00h]
0x140051ad7  mov     rax, [rsi]
0x140051ada  lea     rcx, aSs; "SS"
0x140051ae1  lea     ebp, [r13-1]
0x140051ae5  mov     edx, r13d; Level
0x140051ae8  lea     r9, aHs; "HS"
0x140051aef  lea     r8, aXhcidumpDevice; "XHCIDUMP: Device speed: %s, RootHub por"...
0x140051af6  mov     rbx, [rax+18h]
0x140051afa  nop
0x140051afb  mov     ebx, [rbx]
0x140051afd  mov     edi, ebx
0x140051aff  movups  xmm0, xmmword ptr [rsi+8]
0x140051b03  shr     edi, 18h
0x140051b06  shr     ebx, 10h
0x140051b09  cmp     [rsi+20Ch], ebp
0x140051b0f  mov     [rsi+273h], dil
0x140051b16  cmovnz  r9, rcx
0x140051b1a  mov     [rsi+274h], bl
0x140051b20  mov     byte ptr [rsi+270h], 0
0x140051b27  mov     ecx, r15d; ComponentId
0x140051b2a  mov     eax, [rsi+220h]
0x140051b30  movdqu  [rsp+88h+var_48], xmm0
0x140051b36  mov     dword ptr [rsp+88h+var_68], eax
0x140051b3a  call    cs:__imp_DbgPrintEx
0x140051b41  nop     dword ptr [rax+rax+00h]
0x140051b46  mov     rax, [rsi]
0x140051b49  lea     r14d, [r13-2]
0x140051b4d  movzx   ecx, bl
0x140051b50  lea     r8, aXhcidumpXhciVe; "XHCIDUMP: xHCI version: 0x%x.0x%x, Cont"...
0x140051b57  mov     r9d, edi
0x140051b5a  mov     edx, [rax+68h]
0x140051b5d  mov     eax, [rsi+18h]
0x140051b60  mov     [rsp+88h+var_50], eax
0x140051b64  mov     eax, [rsi+1Ch]
0x140051b67  shr     edx, 2
0x140051b6a  and     edx, r14d
0x140051b6d  mov     [rsp+88h+var_58], eax
0x140051b71  mov     [rsp+88h+var_60], edx
0x140051b75  mov     edx, r13d; Level
0x140051b78  mov     dword ptr [rsp+88h+var_68], ecx
0x140051b7c  mov     ecx, r15d; ComponentId
0x140051b7f  call    cs:__imp_DbgPrintEx
0x140051b86  nop     dword ptr [rax+rax+00h]
0x140051b8b  xor     ebx, ebx
0x140051b8d  mov     rcx, qword ptr [rsp+rbx*8+88h+var_48]
0x140051b92  lea     r8, aXhcidumpDevice_0; "XHCIDUMP: Device Flag[%d]:  0x%I64X\n"
0x140051b99  mov     [rsp+88h+var_68], rcx
0x140051b9e  mov     r9d, ebx
0x140051ba1  mov     ecx, r15d; ComponentId
0x140051ba4  mov     edx, r13d; Level
0x140051ba7  call    cs:__imp_DbgPrintEx
0x140051bae  nop     dword ptr [rax+rax+00h]
0x140051bb3  add     ebx, r14d
0x140051bb6  cmp     ebx, ebp
0x140051bb8  jb      short loc_140051B8D
0x140051bba  mov     eax, [rsi+248h]
0x140051bc0  cmp     eax, ebp
0x140051bc2  jnz     short loc_140051BCD
0x140051bc4  mov     [rsi+248h], r13d
0x140051bcb  jmp     short loc_140051C17
0x140051bcd  dec     eax
0x140051bcf  test    eax, 0FFFFFFFBh
0x140051bd4  jnz     short loc_140051C17
0x140051bd6  mov     rcx, rsi; Address
0x140051bd9  mov     [rsi+272h], r14b
0x140051be0  call    Crashdump_InitializeWithoutControllerReset
0x140051be5  test    eax, eax
0x140051be7  jns     short loc_140051C17
0x140051be9  mov     r9d, eax
0x140051bec  lea     r8, aXhcidumpCrashd_90; "XHCIDUMP: Crashdump_InitializeWithoutCo"...
0x140051bf3  mov     edx, r14d; Level
0x140051bf6  mov     ecx, r15d; ComponentId
0x140051bf9  call    cs:__imp_DbgPrintEx
0x140051c00  nop     dword ptr [rax+rax+00h]
0x140051c05  mov     rcx, rsi
0x140051c08  call    Crashdump_InitializeWithControllerReset
0x140051c0d  mov     ebx, eax
0x140051c0f  test    eax, eax
0x140051c11  js      loc_140051CFD
0x140051c17  mov     rax, [rsi]
0x140051c1a  mov     rax, [rax+20h]
0x140051c1e  nop
0x140051c1f  mov     eax, [rax+4]
0x140051c22  bt      eax, 0Bh
0x140051c26  jnb     short loc_140051C31
0x140051c28  lea     r8, aXhcidumpXhcIsN; "XHCIDUMP: xHC is not ready, cannot cont"...
0x140051c2f  jmp     short loc_140051C4B
0x140051c31  test    al, 4
0x140051c33  jz      short loc_140051C3E
0x140051c35  lea     r8, aXhcidumpHostSy; "XHCIDUMP: Host System Error bit is set,"...
0x140051c3c  jmp     short loc_140051C4B
0x140051c3e  bt      eax, 0Ch
0x140051c42  jnb     short loc_140051C71
0x140051c44  lea     r8, aXhcidumpXhcIsI; "XHCIDUMP: xHC is in an error state, can"...
0x140051c4b  mov     edx, r14d; Level
0x140051c4e  mov     ecx, r15d; ComponentId
0x140051c51  call    cs:__imp_DbgPrintEx
0x140051c58  nop     dword ptr [rax+rax+00h]
0x140051c5d  mov     ebx, 0C0000001h
0x140051c62  lea     r8, aXhcidumpCrashd_89; "XHCIDUMP: Crashdump_Register_VerifyRegi"...
0x140051c69  mov     r9d, ebx
0x140051c6c  jmp     loc_140051D07
0x140051c71  mov     eax, [rsi+248h]
0x140051c77  test    eax, eax
0x140051c79  jz      short loc_140051C86
0x140051c7b  xor     ebx, ebx
0x140051c7d  cmp     eax, r13d
0x140051c80  jnz     loc_140051D19
0x140051c86  mov     edx, [rsi+220h]
0x140051c8c  mov     rcx, rsi
0x140051c8f  call    Crashdump_Register_LogRHPortInfo
0x140051c94  cmp     [rsi+248h], r13d
0x140051c9b  jnz     short loc_140051CEF
0x140051c9d  mov     rbx, [rsi+1F0h]
0x140051ca4  cmp     [rbx], rbx
0x140051ca7  jz      short loc_140051CC7
0x140051ca9  mov     r8d, [rbx+28h]; Size
0x140051cad  xor     edx, edx; Val
0x140051caf  mov     rcx, [rbx+10h]; void *
0x140051cb3  call    memset
0x140051cb8  mov     rbx, [rbx]
0x140051cbb  mov     rax, [rsi+1F0h]
0x140051cc2  cmp     [rbx], rax
0x140051cc5  jnz     short loc_140051CA9
0x140051cc7  mov     rcx, rsi
0x140051cca  call    Crashdump_Register_BiosHandoff
0x140051ccf  test    eax, eax
0x140051cd1  jns     short loc_140051CEF
0x140051cd3  mov     r9d, eax
0x140051cd6  lea     r8, aXhcidumpCrashd_41; "XHCIDUMP: Crashdump_Register_BiosHandof"...
0x140051cdd  mov     edx, r14d; Level
0x140051ce0  mov     ecx, r15d; ComponentId
0x140051ce3  call    cs:__imp_DbgPrintEx
0x140051cea  nop     dword ptr [rax+rax+00h]
0x140051cef  mov     rcx, rsi
0x140051cf2  call    Crashdump_InitializeWithControllerReset
0x140051cf7  mov     ebx, eax
0x140051cf9  test    eax, eax
0x140051cfb  jns     short loc_140051D19
0x140051cfd  mov     r9d, eax
0x140051d00  lea     r8, aXhcidumpCrashd_72; "XHCIDUMP: Crashdump_InitializeWithContr"...
0x140051d07  mov     edx, r14d; Level
0x140051d0a  mov     ecx, r15d; ComponentId
0x140051d0d  call    cs:__imp_DbgPrintEx
0x140051d14  nop     dword ptr [rax+rax+00h]
0x140051d19  mov     eax, [rsi+248h]
0x140051d1f  mov     byte ptr [rsi+271h], 0
0x140051d26  cmp     eax, r14d
0x140051d29  jnz     short loc_140051D33
0x140051d2b  mov     [rsi+248h], ebp
0x140051d31  jmp     short loc_140051D59
0x140051d33  cmp     eax, 5
0x140051d36  jnz     short loc_140051D57
0x140051d38  mov     [rsi+248h], ebp
0x140051d3e  test    byte ptr [rsp+88h+var_48], bpl
0x140051d43  jnz     short loc_140051D68
0x140051d45  cmp     byte ptr [rsi+270h], 0
0x140051d4c  jnz     short loc_140051D68
0x140051d4e  mov     [rsi+271h], r14b
0x140051d55  jmp     short loc_140051D68
0x140051d57  mov     ebp, eax
0x140051d59  cmp     ebp, r13d
0x140051d5c  jnz     short loc_140051D68
0x140051d5e  mov     dword ptr [rsi+248h], 4
0x140051d68  mov     r9d, ebx
0x140051d6b  lea     r8, aXhcidumpCrashd_33; "XHCIDUMP: Crashdump_Initialize: End 0x%"...
0x140051d72  mov     edx, r13d; Level
0x140051d75  mov     ecx, r15d; ComponentId
0x140051d78  call    cs:__imp_DbgPrintEx
0x140051d7f  nop     dword ptr [rax+rax+00h]
0x140051d84  mov     eax, ebx
0x140051d86  add     rsp, 50h
0x140051d8a  pop     r15
0x140051d8c  pop     r14
0x140051d8e  pop     r13
0x140051d90  pop     rdi
0x140051d91  pop     rsi
0x140051d92  pop     rbp
0x140051d93  pop     rbx
0x140051d94  retn
```
