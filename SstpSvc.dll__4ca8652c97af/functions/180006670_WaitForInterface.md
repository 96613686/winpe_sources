# WaitForInterface

- ea: `0x180006670`
- end: `0x18000686a`
- name: `WaitForInterface`
- size: `506`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d50`

## callees

- `0x180006670`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006779`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006779`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006801`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006841`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180006833`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180006833`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800067ed`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1800067ed`

## pseudocode

```c
__int64 __fastcall WaitForInterface(__int64 a1)
{
  __int64 v1; // rax
  HANDLE EventW; // rax
  void *v4; // rdi
  signed int LastError; // eax
  signed int v6; // ebx
  DWORD v7; // eax
  __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v10; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h] BYREF
  DEVPROPKEY v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+8Ch] [rbp-74h]
  __int64 v14; // [rsp+90h] [rbp-70h]
  int v15; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+9Ch] [rbp-64h]
  __int64 v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  int v19; // [rsp+ACh] [rbp-54h]
  DEVPROPKEY v20; // [rsp+B0h] [rbp-50h]
  int v21; // [rsp+C4h] [rbp-3Ch]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  int v23; // [rsp+D0h] [rbp-30h]
  int v24; // [rsp+D4h] [rbp-2Ch]
  char *v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E4h] [rbp-1Ch]
  DEVPROPKEY v28; // [rsp+E8h] [rbp-18h]
  int v29; // [rsp+FCh] [rbp-4h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  int v31; // [rsp+108h] [rbp+8h]
  int v32; // [rsp+10Ch] [rbp+Ch]
  GUID *v33; // [rsp+110h] [rbp+10h]

  v11 = 131074;
  v9 = 0;
  v19 = 0;
  v27 = 0;
  v10 = 0;
  v12 = DEVPKEY_Device_InstanceId;
  v1 = -1;
  v13 = 0;
  v14 = 0;
  v15 = 18;
  while ( *(_WORD *)(a1 + 2 * v1++ + 2) != 0 )
    ;
  v17 = a1;
  v16 = 2 * v1 + 2;
  v20 = DEVPKEY_DeviceInterface_Enabled;
  v25 = s_fDevpropTrue;
  v28 = DEVPKEY_DeviceInterface_ClassGuid;
  v33 = &GUID_DEVINTERFACE_NET;
  v18 = 2;
  v21 = 0;
  v22 = 0;
  v23 = 17;
  v24 = 1;
  v26 = 2;
  v29 = 0;
  v30 = 0;
  v31 = 13;
  v32 = 16;
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = EventW;
  if ( !EventW )
    goto LABEL_4;
  *(_QWORD *)&v10 = EventW;
  DWORD2(v10) = 0;
  v6 = DevCreateObjectQuery(1, 1, 0, 0, 3, &v11, DevQueryCallback, &v10, &v9);
  if ( v6 < 0 )
    goto LABEL_12;
  v7 = WaitForSingleObject(v4, 0x7530u);
  if ( !v7 )
  {
    v6 = DWORD2(v10);
    goto LABEL_12;
  }
  if ( v7 == -1 )
  {
LABEL_4:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = -2147418113;
    if ( v7 == 258 )
      v6 = DWORD2(v10);
  }
LABEL_12:
  if ( v9 )
    DevCloseObjectQuery();
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006670  mov     [rsp-8+arg_0], rbx
0x180006675  mov     [rsp-8+arg_8], rdi
0x18000667a  push    rbp
0x18000667b  lea     rbp, [rsp-30h]
0x180006680  sub     rsp, 130h
0x180006687  mov     rax, cs:__security_cookie
0x18000668e  xor     rax, rsp
0x180006691  mov     [rbp+30h+var_10], rax
0x180006695  xor     ebx, ebx
0x180006697  mov     [rsp+130h+var_C0], 20002h
0x1800066a0  xor     eax, eax
0x1800066a2  mov     [rsp+130h+var_E0], rbx
0x1800066a7  xorps   xmm0, xmm0
0x1800066aa  mov     [rbp+30h+var_84], eax
0x1800066ad  mov     [rbp+30h+var_4C], eax
0x1800066b0  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x1800066b6  movups  [rsp+130h+var_D8], xmm0
0x1800066bb  mov     [rbp+30h+var_A8], eax
0x1800066be  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800066c5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x1800066cc  mov     [rbp+30h+var_A4], ebx
0x1800066cf  mov     [rbp+30h+var_A0], rbx
0x1800066d3  movups  [rsp+130h+var_B8], xmm0
0x1800066d8  mov     [rbp+30h+var_98], 12h
0x1800066df  nop
0x1800066e0  cmp     [rcx+rax*2+2], bx
0x1800066e5  lea     rax, [rax+1]
0x1800066e9  jnz     short loc_1800066E0
0x1800066eb  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x1800066f2  lea     eax, ds:2[rax*2]
0x1800066f9  mov     [rbp+30h+var_90], rcx
0x1800066fd  mov     [rbp+30h+var_94], eax
0x180006700  xor     r9d, r9d; lpName
0x180006703  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180006709  xor     r8d, r8d; bInitialState
0x18000670c  mov     [rbp+30h+var_70], eax
0x18000670f  xor     edx, edx; bManualReset
0x180006711  lea     rax, s_fDevpropTrue
0x180006718  movaps  [rbp+30h+var_80], xmm0
0x18000671c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180006723  mov     [rbp+30h+var_58], rax
0x180006727  xor     ecx, ecx; lpEventAttributes
0x180006729  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18000672f  mov     [rbp+30h+var_38], eax
0x180006732  lea     rax, GUID_DEVINTERFACE_NET
0x180006739  mov     [rbp+30h+var_20], rax
0x18000673d  mov     [rbp+30h+var_88], 2
0x180006744  mov     [rbp+30h+var_6C], ebx
0x180006747  mov     [rbp+30h+var_68], rbx
0x18000674b  mov     [rbp+30h+var_60], 11h
0x180006752  mov     [rbp+30h+var_5C], 1
0x180006759  mov     [rbp+30h+var_50], 2
0x180006760  movups  [rbp+30h+var_48], xmm0
0x180006764  mov     [rbp+30h+var_34], ebx
0x180006767  mov     [rbp+30h+var_30], rbx
0x18000676b  mov     [rbp+30h+var_28], 0Dh
0x180006772  mov     [rbp+30h+var_24], 10h
0x180006779  call    cs:__imp_CreateEventW
0x18000677f  mov     rdi, rax
0x180006782  test    rax, rax
0x180006785  jnz     short loc_1800067A5
0x180006787  call    cs:__imp_GetLastError
0x18000678d  mov     ebx, eax
0x18000678f  test    eax, eax
0x180006791  jle     loc_180006829
0x180006797  movzx   ebx, ax
0x18000679a  or      ebx, 80070000h
0x1800067a0  jmp     loc_180006829
0x1800067a5  lea     rax, [rsp+130h+var_E0]
0x1800067aa  mov     qword ptr [rsp+130h+var_D8], rdi
0x1800067af  mov     [rsp+130h+var_F0], rax
0x1800067b4  mov     edx, 1
0x1800067b9  lea     rax, [rsp+130h+var_D8]
0x1800067be  mov     dword ptr [rsp+130h+var_D8+8], ebx
0x1800067c2  mov     [rsp+130h+var_F8], rax
0x1800067c7  xor     r9d, r9d
0x1800067ca  lea     rax, DevQueryCallback
0x1800067d1  xor     r8d, r8d
0x1800067d4  mov     [rsp+130h+var_100], rax
0x1800067d9  mov     ecx, edx
0x1800067db  lea     rax, [rsp+130h+var_C0]
0x1800067e0  mov     [rsp+130h+var_108], rax
0x1800067e5  mov     [rsp+130h+var_110], 3
0x1800067ed  call    cs:__imp_DevCreateObjectQuery
0x1800067f3  mov     ebx, eax
0x1800067f5  test    eax, eax
0x1800067f7  js      short loc_180006829
0x1800067f9  mov     edx, 7530h; dwMilliseconds
0x1800067fe  mov     rcx, rdi; hHandle
0x180006801  call    cs:__imp_WaitForSingleObject
0x180006807  test    eax, eax
0x180006809  jnz     short loc_180006811
0x18000680b  mov     ebx, dword ptr [rsp+130h+var_D8+8]
0x18000680f  jmp     short loc_180006829
0x180006811  cmp     eax, 0FFFFFFFFh
0x180006814  jz      loc_180006787
0x18000681a  cmp     eax, 102h
0x18000681f  mov     ebx, 8000FFFFh
0x180006824  cmovz   ebx, dword ptr [rsp+130h+var_D8+8]
0x180006829  mov     rcx, [rsp+130h+var_E0]
0x18000682e  test    rcx, rcx
0x180006831  jz      short loc_180006839
0x180006833  call    cs:__imp_DevCloseObjectQuery
0x180006839  test    rdi, rdi
0x18000683c  jz      short loc_180006847
0x18000683e  mov     rcx, rdi; hObject
0x180006841  call    cs:__imp_CloseHandle
0x180006847  mov     eax, ebx
0x180006849  mov     rcx, [rbp+30h+var_10]
0x18000684d  xor     rcx, rsp; StackCookie
0x180006850  call    __security_check_cookie
0x180006855  lea     r11, [rsp+130h+var_s0]
0x18000685d  mov     rbx, [r11+10h]
0x180006861  mov     rdi, [r11+18h]
0x180006865  mov     rsp, r11
0x180006868  pop     rbp
0x180006869  retn
```
