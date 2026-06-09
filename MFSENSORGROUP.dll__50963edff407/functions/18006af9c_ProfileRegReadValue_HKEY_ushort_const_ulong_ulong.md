# ProfileRegReadValue(HKEY__ *,ushort const *,ulong *,ulong)

- ea: `0x18006af9c`
- end: `0x18006b0c3`
- name: `?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAKK@Z`
- size: `295`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800419a0`
- `0x180069a9c`

## callees

- `0x180005fa0`
- `0x18006af9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006b035`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006b035`
- `MFPlat!MFTraceError` at `0x18006b06e`
- `MFPlat!MFTraceError` at `0x18006b0a5`
- `MFPlat!MFTraceError` at `0x18006b06e`
- `MFPlat!MFTraceError` at `0x18006b0a5`

## string_xrefs

- `0x18006b054`: `ProfileRegReadValue`
- `0x18006b092`: `ProfileRegReadValue`

## pseudocode

```c
__int64 __fastcall ProfileRegReadValue(HKEY a1, const unsigned __int16 *a2, unsigned int *pvData)
{
  unsigned int v4; // ebx
  LSTATUS ValueW; // eax
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF

  pcbData = 4;
  if ( (unsigned __int64)a1 - 1 > 0xFFFFFFFFFFFFFFFDuLL || !a2 )
  {
    v4 = -2147024809;
    MFTraceError(
      "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
      838,
      "ProfileRegReadValue",
      0,
      -2147024809,
      1);
LABEL_13:
    if ( pvData )
      *pvData = 0;
    return v4;
  }
  if ( !pvData )
  {
    v4 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
        0,
        -2147467261);
    return v4;
  }
  *pvData = 0;
  ValueW = RegGetValueW(a1, 0, a2, 0x10u, 0, pvData, &pcbData);
  v4 = ValueW;
  if ( !ValueW )
    return 0;
  if ( ValueW > 0 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
  MFTraceError("avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp", 848, "ProfileRegReadValue", 0, v4, 1);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_13;
  return v4;
}

```

## disassembly

```asm
0x18006af9c  mov     [rsp+arg_0], rbx
0x18006afa1  mov     [rsp+arg_18], r9d
0x18006afa6  push    rdi
0x18006afa7  sub     rsp, 40h
0x18006afab  lea     rax, [rcx-1]
0x18006afaf  mov     [rsp+48h+arg_18], 4
0x18006afb7  mov     rdi, r8
0x18006afba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006afbe  ja      loc_18006B07E
0x18006afc4  test    rdx, rdx
0x18006afc7  jz      loc_18006B07E
0x18006afcd  test    r8, r8
0x18006afd0  jnz     short loc_18006B00B
0x18006afd2  mov     ebx, 80004003h
0x18006afd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006afde  jb      loc_18006B0B6
0x18006afe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006afeb  lea     edx, [r8+45h]
0x18006afef  xor     r9d, r9d
0x18006aff2  mov     dword ptr [rsp+48h+pdwType], ebx
0x18006aff6  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006affd  mov     rcx, [rcx+10h]
0x18006b001  call    WPP_SF_qD
0x18006b006  jmp     loc_18006B0B6
0x18006b00b  lea     rax, [rsp+48h+arg_18]
0x18006b010  mov     dword ptr [r8], 0
0x18006b017  mov     [rsp+48h+pcbData], rax; pcbData
0x18006b01c  mov     r8, rdx; lpValue
0x18006b01f  mov     [rsp+48h+pvData], rdi; pvData
0x18006b024  mov     r9d, 10h; dwFlags
0x18006b02a  xor     edx, edx; lpSubKey
0x18006b02c  mov     [rsp+48h+pdwType], 0; pdwType
0x18006b035  call    cs:__imp_RegGetValueW
0x18006b03b  mov     ebx, eax
0x18006b03d  test    eax, eax
0x18006b03f  jz      short loc_18006B07A
0x18006b041  jle     short loc_18006B04C
0x18006b043  movzx   ebx, ax
0x18006b046  or      ebx, 80070000h
0x18006b04c  mov     dword ptr [rsp+48h+pvData], 1
0x18006b054  lea     r8, aProfileregread; "ProfileRegReadValue"
0x18006b05b  xor     r9d, r9d
0x18006b05e  mov     dword ptr [rsp+48h+pdwType], ebx
0x18006b062  mov     edx, 350h
0x18006b067  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x18006b06e  call    cs:__imp_MFTraceError
0x18006b074  test    ebx, ebx
0x18006b076  jns     short loc_18006B0B6
0x18006b078  jmp     short loc_18006B0AB
0x18006b07a  xor     ebx, ebx
0x18006b07c  jmp     short loc_18006B0B6
0x18006b07e  mov     ebx, 80070057h
0x18006b083  mov     dword ptr [rsp+48h+pvData], 1
0x18006b08b  xor     r9d, r9d
0x18006b08e  mov     dword ptr [rsp+48h+pdwType], ebx
0x18006b092  lea     r8, aProfileregread; "ProfileRegReadValue"
0x18006b099  mov     edx, 346h
0x18006b09e  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x18006b0a5  call    cs:__imp_MFTraceError
0x18006b0ab  test    rdi, rdi
0x18006b0ae  jz      short loc_18006B0B6
0x18006b0b0  mov     dword ptr [rdi], 0
0x18006b0b6  mov     eax, ebx
0x18006b0b8  mov     rbx, [rsp+48h+arg_0]
0x18006b0bd  add     rsp, 40h
0x18006b0c1  pop     rdi
0x18006b0c2  retn
```
