# Command_PrepareHardware

- ea: `0x140075f20`
- end: `0x1400760a0`
- name: `Command_PrepareHardware`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14007a8f0`

## callees

- `0x14001ad0c`
- `0x1400290e0`
- `0x14003f53c`
- `0x14003f87c`
- `0x14003f9f8`
- `0x14003fa18`
- `0x140059970`
- `0x140075f20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140075fdd`
- `ntoskrnl!ExAllocatePool2` at `0x140075fdd`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140076077`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140076077`

## pseudocode

```c
__int64 __fastcall Command_PrepareHardware(__int64 a1)
{
  int Resources; // edi
  unsigned int MaxTrbIndex; // eax
  __int64 v4; // rcx
  int v5; // edx
  __int64 *v6; // rdi
  __int64 Pool2; // rax
  __int64 v9; // r9
  char v10; // [rsp+28h] [rbp-50h]
  __int128 v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h]
  char pszDest[16]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v14; // [rsp+60h] [rbp-18h]

  v11 = 0;
  v14 = 0;
  v12 = 0;
  *(_OWORD *)pszDest = 0;
  Resources = XilCommand_AllocateResources();
  if ( Resources < 0 )
    goto LABEL_6;
  *(_QWORD *)(a1 + 88) = a1 + 80;
  *(_QWORD *)(a1 + 80) = a1 + 80;
  *(_QWORD *)(a1 + 104) = a1 + 96;
  *(_QWORD *)(a1 + 96) = a1 + 96;
  MaxTrbIndex = XilCommand_GetMaxTrbIndex(a1);
  *(_DWORD *)(a1 + 48) = MaxTrbIndex;
  *(_QWORD *)(a1 + 56) = XilCommand_GetLinkTrbPointer(v4, MaxTrbIndex);
  v6 = (__int64 *)(a1 + 8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = v5;
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_d(*(_QWORD *)(*v6 + 72), v5, 7, 13, (__int64)WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids, v10);
  }
  Pool2 = ExAllocatePool2(64, 16LL * (unsigned int)(*(_DWORD *)(a1 + 48) + 1), 1229146200);
  *(_QWORD *)(a1 + 72) = Pool2;
  if ( !Pool2 )
  {
    Resources = -1073741670;
LABEL_6:
    XilCommand_FreeResources(a1);
    return (unsigned int)Resources;
  }
  v9 = *v6;
  *(_QWORD *)&v11 = 56;
  pszDest[0] = 0;
  HIDWORD(v12) = 16;
  *(_QWORD *)&v12 = 0;
  BYTE8(v12) = 0;
  v14 = 0x200000002LL;
  *((_QWORD *)&v11 + 1) = 0xC800000400LL;
  RtlStringCchPrintfA(pszDest, 0x10u, "%02d CMD", *(_DWORD *)(v9 + 176));
  if ( (int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v11, a1 + 16) < 0 )
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(*v6 + 72);
  *(_DWORD *)(a1 + 32) = 1;
  return 0;
}

```

## disassembly

```asm
0x140075f20  push    rbp
0x140075f22  push    rbx
0x140075f23  push    rsi
0x140075f24  push    rdi
0x140075f25  mov     rbp, rsp
0x140075f28  sub     rsp, 78h
0x140075f2c  mov     rax, cs:__security_cookie
0x140075f33  xor     rax, rsp
0x140075f36  mov     [rbp+var_10], rax
0x140075f3a  xorps   xmm0, xmm0
0x140075f3d  xor     eax, eax
0x140075f3f  movups  [rbp+var_48], xmm0
0x140075f43  mov     [rbp+var_18], rax
0x140075f47  mov     rbx, rcx
0x140075f4a  movups  [rbp+var_38], xmm0
0x140075f4e  movups  xmmword ptr [rbp+pszDest], xmm0
0x140075f52  call    XilCommand_AllocateResources
0x140075f57  mov     edi, eax
0x140075f59  test    eax, eax
0x140075f5b  js      loc_140075FF7
0x140075f61  lea     rax, [rbx+50h]
0x140075f65  mov     rcx, rbx
0x140075f68  mov     [rax+8], rax
0x140075f6c  mov     [rax], rax
0x140075f6f  lea     rax, [rbx+60h]
0x140075f73  mov     [rax+8], rax
0x140075f77  mov     [rax], rax
0x140075f7a  call    XilCommand_GetMaxTrbIndex
0x140075f7f  mov     edx, eax
0x140075f81  mov     [rbx+30h], eax
0x140075f84  call    XilCommand_GetLinkTrbPointer
0x140075f89  mov     [rbx+38h], rax
0x140075f8d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140075f94  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140075f9b  lea     rdi, [rbx+8]
0x140075f9f  jz      short loc_140075FC9
0x140075fa1  mov     rcx, [rdi]
0x140075fa4  lea     rax, WPP_07dbab66191e3ae246eda25bdcd833c6_Traceguids
0x140075fab  mov     dword ptr [rsp+78h+var_50], edx
0x140075faf  mov     r9d, 0Dh
0x140075fb5  mov     dl, 4
0x140075fb7  mov     [rsp+78h+var_58], rax
0x140075fbc  mov     rcx, [rcx+48h]
0x140075fc0  lea     r8d, [r9-6]
0x140075fc4  call    WPP_RECORDER_SF_d
0x140075fc9  mov     edx, [rbx+30h]
0x140075fcc  mov     ecx, 40h ; '@'
0x140075fd1  inc     edx
0x140075fd3  mov     r8d, 49434858h
0x140075fd9  shl     rdx, 4
0x140075fdd  call    cs:__imp_ExAllocatePool2
0x140075fe4  nop     dword ptr [rax+rax+00h]
0x140075fe9  mov     [rbx+48h], rax
0x140075fed  test    rax, rax
0x140075ff0  jnz     short loc_140076017
0x140075ff2  mov     edi, 0C000009Ah
0x140075ff7  mov     rcx, rbx
0x140075ffa  call    XilCommand_FreeResources
0x140075fff  mov     eax, edi
0x140076001  mov     rcx, [rbp+var_10]
0x140076005  xor     rcx, rsp; StackCookie
0x140076008  call    __security_check_cookie
0x14007600d  add     rsp, 78h
0x140076011  pop     rdi
0x140076012  pop     rsi
0x140076013  pop     rbx
0x140076014  pop     rbp
0x140076015  retn
0x140076017  mov     r9, [rdi]
0x14007601a  lea     r8, a02dCmd; "%02d CMD"
0x140076021  mov     edx, 10h; cchDest
0x140076026  mov     qword ptr [rbp+var_48], 38h ; '8'
0x14007602e  mov     [rbp+pszDest], 0
0x140076032  lea     rcx, [rbp+pszDest]; pszDest
0x140076036  mov     dword ptr [rbp+var_38+0Ch], edx
0x140076039  mov     qword ptr [rbp+var_38], 0
0x140076041  lea     eax, [rdx-0Eh]
0x140076044  mov     byte ptr [rbp+var_38+8], 0
0x140076048  mov     dword ptr [rbp+var_18], eax
0x14007604b  mov     dword ptr [rbp+var_18+4], eax
0x14007604e  mov     dword ptr [rbp+var_48+8], 400h
0x140076055  mov     dword ptr [rbp+var_48+0Ch], 0C8h
0x14007605c  mov     r9d, [r9+0B0h]
0x140076063  call    RtlStringCchPrintfA
0x140076068  mov     rcx, cs:WPP_GLOBAL_Control
0x14007606f  lea     r8, [rbx+10h]
0x140076073  lea     rdx, [rbp+var_48]
0x140076077  call    cs:__imp_imp_WppRecorderLogCreate
0x14007607e  nop     dword ptr [rax+rax+00h]
0x140076083  test    eax, eax
0x140076085  jns     short loc_140076092
0x140076087  mov     rax, [rdi]
0x14007608a  mov     rcx, [rax+48h]
0x14007608e  mov     [rbx+10h], rcx
0x140076092  mov     dword ptr [rbx+20h], 1
0x140076099  xor     edi, edi
0x14007609b  jmp     loc_140075FFF
```
