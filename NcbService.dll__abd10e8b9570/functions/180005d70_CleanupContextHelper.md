# CleanupContextHelper

- ea: `0x180005d70`
- end: `0x180006045`
- name: `CleanupContextHelper`
- size: `725`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002c30`
- `0x180005b78`
- `0x18000cae0`
- `0x18000d970`
- `0x180014430`

## callees

- `0x180003ed0`
- `0x180003f00`
- `0x180005d70`
- `0x18000a160`
- `0x180017b94`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005eca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df8`
- `NSI!NsiSetAllParameters` at `0x180005ead`
- `NSI!NsiSetAllParameters` at `0x180005ead`

## pseudocode

```c
__int64 __fastcall CleanupContextHelper(char *lpMem)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // edi
  unsigned int v15; // [rsp+40h] [rbp-78h] BYREF
  __int128 v16; // [rsp+48h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+58h] [rbp-60h] BYREF
  const wchar_t *v18; // [rsp+68h] [rbp-50h]
  __int64 v19; // [rsp+70h] [rbp-48h]
  int *v20; // [rsp+78h] [rbp-40h]
  __int64 v21; // [rsp+80h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  v16 = 0;
  KamDestroyTimer((__int64)lpMem);
  v2 = (void *)*((_QWORD *)lpMem + 27);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)lpMem + 27) = 0;
  }
  v3 = (void *)*((_QWORD *)lpMem + 28);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)lpMem + 28) = 0;
  }
  v4 = (void *)*((_QWORD *)lpMem + 25);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)lpMem + 25) = 0;
  }
  v5 = (void *)*((_QWORD *)lpMem + 34);
  if ( v5 )
  {
    VpnFree(v5);
    *((_QWORD *)lpMem + 34) = 0;
  }
  v6 = (void *)*((_QWORD *)lpMem + 32);
  if ( v6 )
  {
    VpnFree(v6);
    *((_QWORD *)lpMem + 32) = 0;
  }
  v7 = (void *)*((_QWORD *)lpMem + 30);
  if ( v7 )
  {
    VpnFree(v7);
    *((_QWORD *)lpMem + 30) = 0;
  }
  v8 = (void *)*((_QWORD *)lpMem + 31);
  if ( v8 )
  {
    VpnFree(v8);
    *((_QWORD *)lpMem + 31) = 0;
  }
  v9 = (void *)*((_QWORD *)lpMem + 35);
  if ( v9 )
  {
    VpnFree(v9);
    *((_QWORD *)lpMem + 35) = 0;
  }
  LODWORD(v16) = *((_DWORD *)lpMem + 49);
  *((_QWORD *)&v16 + 1) = *((_QWORD *)lpMem + 52);
  v10 = NsiSetAllParameters(1, 3, NPI_MS_TCP_MODULEID, 31, &v16, 16, 0, 0);
  v13 = v10;
  if ( v10 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v15 = v10;
      v18 = L"NcbReg: Failed to clear wpm context";
      v19 = 72;
      v20 = (int *)&v15;
      v21 = 4;
      McGenEventWrite_EventWriteTransfer(v11, (const EVENT_DESCRIPTOR *)NcbApiStatus, v12, 3u, &v17);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v13);
    }
  }
  if ( !lpMem[340] && !lpMem[360] )
    CloseBiEvent(lpMem + 324);
  DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 24));
  VpnFree(lpMem);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180005d70  push    rbx
0x180005d72  push    rbp
0x180005d73  push    rsi
0x180005d74  push    rdi
0x180005d75  sub     rsp, 98h
0x180005d7c  mov     rax, cs:__security_cookie
0x180005d83  xor     rax, rsp
0x180005d86  mov     [rsp+0B8h+var_30], rax
0x180005d8e  mov     rbx, rcx
0x180005d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d98  lea     rbp, WPP_GLOBAL_Control
0x180005d9f  cmp     rcx, rbp
0x180005da2  jnz     loc_180005F48
0x180005da8  xorps   xmm0, xmm0
0x180005dab  mov     rcx, rbx
0x180005dae  movups  [rsp+0B8h+var_70], xmm0
0x180005db3  call    KamDestroyTimer
0x180005db8  mov     rcx, [rbx+0D8h]; hObject
0x180005dbf  xor     esi, esi
0x180005dc1  test    rcx, rcx
0x180005dc4  jz      short loc_180005DD3
0x180005dc6  call    cs:__imp_CloseHandle
0x180005dcc  mov     [rbx+0D8h], rsi
0x180005dd3  mov     rcx, [rbx+0E0h]; hObject
0x180005dda  test    rcx, rcx
0x180005ddd  jz      short loc_180005DEC
0x180005ddf  call    cs:__imp_CloseHandle
0x180005de5  mov     [rbx+0E0h], rsi
0x180005dec  mov     rcx, [rbx+0C8h]; hObject
0x180005df3  test    rcx, rcx
0x180005df6  jz      short loc_180005E05
0x180005df8  call    cs:__imp_CloseHandle
0x180005dfe  mov     [rbx+0C8h], rsi
0x180005e05  mov     rcx, [rbx+110h]; lpMem
0x180005e0c  test    rcx, rcx
0x180005e0f  jz      short loc_180005E1D
0x180005e11  call    VpnFree
0x180005e16  mov     [rbx+110h], rsi
0x180005e1d  mov     rcx, [rbx+100h]; lpMem
0x180005e24  test    rcx, rcx
0x180005e27  jnz     loc_180006012
0x180005e2d  mov     rcx, [rbx+0F0h]; lpMem
0x180005e34  test    rcx, rcx
0x180005e37  jnz     loc_180006023
0x180005e3d  mov     rcx, [rbx+0F8h]; lpMem
0x180005e44  test    rcx, rcx
0x180005e47  jnz     loc_180006034
0x180005e4d  mov     rcx, [rbx+118h]; lpMem
0x180005e54  test    rcx, rcx
0x180005e57  jz      short loc_180005E65
0x180005e59  call    VpnFree
0x180005e5e  mov     [rbx+118h], rsi
0x180005e65  mov     eax, [rbx+0C4h]
0x180005e6b  lea     r8, NPI_MS_TCP_MODULEID
0x180005e72  mov     dword ptr [rsp+0B8h+var_70], eax
0x180005e76  mov     r9d, 1Fh
0x180005e7c  mov     rax, [rbx+1A0h]
0x180005e83  mov     edx, 3
0x180005e88  mov     [rsp+0B8h+var_80], esi
0x180005e8c  mov     ecx, 1
0x180005e91  mov     qword ptr [rsp+0B8h+var_70+8], rax
0x180005e96  lea     rax, [rsp+0B8h+var_70]
0x180005e9b  mov     [rsp+0B8h+var_88], rsi
0x180005ea0  mov     [rsp+0B8h+var_90], 10h
0x180005ea8  mov     [rsp+0B8h+var_98], rax
0x180005ead  call    cs:__imp_NsiSetAllParameters
0x180005eb3  mov     edi, eax
0x180005eb5  test    eax, eax
0x180005eb7  jnz     short loc_180005F06
0x180005eb9  cmp     [rbx+154h], sil
0x180005ec0  jz      loc_180005FA4
0x180005ec6  lea     rcx, [rbx+18h]; lpCriticalSection
0x180005eca  call    cs:__imp_DeleteCriticalSection
0x180005ed0  mov     rcx, rbx; lpMem
0x180005ed3  call    VpnFree
0x180005ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005edf  cmp     rcx, rbp
0x180005ee2  jnz     loc_180005F76
0x180005ee8  xor     eax, eax
0x180005eea  mov     rcx, [rsp+0B8h+var_30]
0x180005ef2  xor     rcx, rsp; StackCookie
0x180005ef5  call    __security_check_cookie
0x180005efa  add     rsp, 98h
0x180005f01  pop     rdi
0x180005f02  pop     rsi
0x180005f03  pop     rbp
0x180005f04  pop     rbx
0x180005f05  retn
0x180005f06  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180005f0d  jnz     loc_180005FC2
0x180005f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f1a  cmp     rcx, rbp
0x180005f1d  jz      short loc_180005EB9
0x180005f1f  test    byte ptr [rcx+1Ch], 1
0x180005f23  jz      short loc_180005EB9
0x180005f25  cmp     byte ptr [rcx+19h], 2
0x180005f29  jb      short loc_180005EB9
0x180005f2b  mov     rcx, [rcx+10h]
0x180005f2f  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180005f36  mov     edx, 82h
0x180005f3b  mov     r9d, edi
0x180005f3e  call    WPP_SF_d
0x180005f43  jmp     loc_180005EB9
0x180005f48  test    byte ptr [rcx+1Ch], 1
0x180005f4c  jz      loc_180005DA8
0x180005f52  cmp     byte ptr [rcx+19h], 6
0x180005f56  jb      loc_180005DA8
0x180005f5c  mov     rcx, [rcx+10h]
0x180005f60  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180005f67  mov     edx, 81h
0x180005f6c  call    WPP_SF_
0x180005f71  jmp     loc_180005DA8
0x180005f76  test    byte ptr [rcx+1Ch], 1
0x180005f7a  jz      loc_180005EE8
0x180005f80  cmp     byte ptr [rcx+19h], 6
0x180005f84  jb      loc_180005EE8
0x180005f8a  mov     rcx, [rcx+10h]
0x180005f8e  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180005f95  mov     edx, 83h
0x180005f9a  call    WPP_SF_
0x180005f9f  jmp     loc_180005EE8
0x180005fa4  cmp     [rbx+168h], sil
0x180005fab  jnz     loc_180005EC6
0x180005fb1  lea     rcx, [rbx+144h]
0x180005fb8  call    CloseBiEvent
0x180005fbd  jmp     loc_180005EC6
0x180005fc2  lea     rax, aNcbregFailedTo_8; "NcbReg: Failed to clear wpm context"
0x180005fc9  mov     [rsp+0B8h+var_78], edi
0x180005fcd  mov     [rsp+0B8h+var_50], rax
0x180005fd2  lea     rdx, NcbApiStatus
0x180005fd9  lea     rax, [rsp+0B8h+var_78]
0x180005fde  mov     [rsp+0B8h+var_48], 48h ; 'H'
0x180005fe7  mov     [rsp+0B8h+var_40], rax
0x180005fec  mov     r9d, 3
0x180005ff2  lea     rax, [rsp+0B8h+var_60]
0x180005ff7  mov     [rsp+0B8h+var_38], 4
0x180006003  mov     [rsp+0B8h+var_98], rax
0x180006008  call    McGenEventWrite_EventWriteTransfer
0x18000600d  jmp     loc_180005F13
0x180006012  call    VpnFree
0x180006017  mov     [rbx+100h], rsi
0x18000601e  jmp     loc_180005E2D
0x180006023  call    VpnFree
0x180006028  mov     [rbx+0F0h], rsi
0x18000602f  jmp     loc_180005E3D
0x180006034  call    VpnFree
0x180006039  mov     [rbx+0F8h], rsi
0x180006040  jmp     loc_180005E4D
```
