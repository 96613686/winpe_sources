# VmSwitchNetSetupPlugin::TryGetSwitchInfoByMiniportId(_NETSETUP_OBJECT_ID const &,_VMS_ENUM_SWITCH_INFO_OUT &)

- ea: `0x18007f254`
- end: `0x18007f59a`
- name: `?TryGetSwitchInfoByMiniportId@VmSwitchNetSetupPlugin@@AEAA_NAEBU_NETSETUP_OBJECT_ID@@AEAU_VMS_ENUM_SWITCH_INFO_OUT@@@Z`
- size: `838`
- prototype: `bool __fastcall(VmSwitchNetSetupPlugin *__hidden this, const struct _NETSETUP_OBJECT_ID *, struct _VMS_ENUM_SWITCH_INFO_OUT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002ef78`

## callees

- `0x18001dee8`
- `0x18005b034`
- `0x18005c848`
- `0x180064704`
- `0x180065056`
- `0x180065928`
- `0x18007edf8`
- `0x18007f254`
- `0x18007f5a0`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f43d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f43d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f53f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007f2b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007f2b9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007f347`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007f433`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007f347`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007f433`

## pseudocode

```c
char __fastcall VmSwitchNetSetupPlugin::TryGetSwitchInfoByMiniportId(
        VmSwitchNetSetupPlugin *this,
        const struct _NETSETUP_OBJECT_ID *a2,
        struct _VMS_ENUM_SWITCH_INFO_OUT *a3)
{
  DWORD v3; // edi
  char v4; // bl
  char *v6; // rsi
  HANDLE FileW; // r12
  DWORD LastError; // eax
  DWORD v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  VmSwitchNetSetupPlugin *v16; // rcx
  DWORD v17; // eax
  DWORD v18; // ebx
  const wchar_t *v19; // r15
  __int64 v20; // rax
  unsigned int OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+54h] [rbp-1Ch] BYREF
  struct _GUID v25; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  v4 = 0;
  v6 = 0;
  VerifyOnline(*(_QWORD *)this);
  FileW = CreateFileW(L"\\\\.\\VmSwitch", 0xC0000000, 0, 0, 3u, 0x100080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, LastError);
    }
  }
  else
  {
    OutBuffer = 0;
    BytesReturned = 0;
    if ( DeviceIoControl(FileW, 0x222014u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
    {
      v13 = OutBuffer;
      if ( OutBuffer )
      {
        while ( 1 )
        {
          v15 = v13;
          v14 = 3640LL * v13;
          if ( !is_mul_ok(v15, 0xE38u) )
            v14 = -1;
          v6 = (char *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v6 )
            break;
          if ( DeviceIoControl(FileW, 0x222018u, 0, 0, v6, 3640 * OutBuffer, &BytesReturned, 0) )
          {
            v18 = BytesReturned / 0xE38;
            while ( v3 < v18 )
            {
              v25 = 0;
              v19 = (const wchar_t *)&v6[3640 * v3];
              if ( !VmSwitchNetSetupPlugin::ParseGuidFromDeviceString(v16, v19 + 1674, &v25) )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    39,
                    WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids,
                    v19 + 1674);
                break;
              }
              v20 = *(_QWORD *)&v25.Data1 - *(_QWORD *)((char *)a2 + 4);
              if ( *(_QWORD *)&v25.Data1 == *(_QWORD *)((char *)a2 + 4) )
                v20 = *(_QWORD *)v25.Data4 - *(_QWORD *)((char *)a2 + 12);
              if ( !v20 )
              {
                memcpy_0(a3, v19, 0xE38u);
                v4 = 1;
                goto LABEL_35;
              }
              ++v3;
            }
            v4 = 0;
            goto LABEL_35;
          }
          v17 = GetLastError();
          v12 = v17;
          if ( v17 != 122 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = 38;
              goto LABEL_9;
            }
            goto LABEL_35;
          }
          operator delete(v6);
          v13 = 2 * OutBuffer;
          OutBuffer *= 2;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = OutBuffer;
          v11 = 37;
          goto LABEL_9;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = GetLastError();
      v10 = WPP_GLOBAL_Control;
      v11 = 35;
      v12 = v9;
LABEL_9:
      WPP_SF_d(v10[2], v11, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, v12);
    }
LABEL_35:
    CloseHandle(FileW);
  }
  operator delete(v6);
  return v4;
}

```

## disassembly

```asm
0x18007f254  mov     [rsp-38h+arg_8], rbx
0x18007f259  push    rbp
0x18007f25a  push    rsi
0x18007f25b  push    rdi
0x18007f25c  push    r12
0x18007f25e  push    r13
0x18007f260  push    r14
0x18007f262  push    r15
0x18007f264  mov     rbp, rsp
0x18007f267  sub     rsp, 70h
0x18007f26b  mov     rax, cs:__security_cookie
0x18007f272  xor     rax, rsp
0x18007f275  mov     [rbp+var_8], rax
0x18007f279  mov     rcx, [rcx]
0x18007f27c  xor     edi, edi
0x18007f27e  mov     bl, dil
0x18007f281  mov     [rbp+var_28], r8
0x18007f285  mov     [rbp+var_30], bl
0x18007f288  mov     r13, rdx
0x18007f28b  mov     esi, edi
0x18007f28d  call    VerifyOnline
0x18007f292  mov     [rsp+70h+hTemplateFile], rdi; hTemplateFile
0x18007f297  lea     rcx, FileName; "\\\\.\\VmSwitch"
0x18007f29e  mov     [rsp+70h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18007f2a6  xor     r9d, r9d; lpSecurityAttributes
0x18007f2a9  xor     r8d, r8d; dwShareMode
0x18007f2ac  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18007f2b4  mov     edx, 0C0000000h; dwDesiredAccess
0x18007f2b9  call    cs:__imp_CreateFileW
0x18007f2bf  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007f2c3  mov     r12, rax
0x18007f2c6  cmp     rax, r14
0x18007f2c9  jnz     short loc_18007F314
0x18007f2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f2d2  lea     rax, WPP_GLOBAL_Control
0x18007f2d9  cmp     rcx, rax
0x18007f2dc  jz      loc_18007F545
0x18007f2e2  cmp     byte ptr [rcx+19h], 2
0x18007f2e6  jb      loc_18007F545
0x18007f2ec  call    cs:__imp_GetLastError
0x18007f2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f2f9  lea     edx, [rdi+22h]
0x18007f2fc  mov     r9d, eax
0x18007f2ff  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f306  mov     rcx, [rcx+10h]
0x18007f30a  call    WPP_SF_d
0x18007f30f  jmp     loc_18007F545
0x18007f314  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x18007f319  lea     rax, [rbp+BytesReturned]
0x18007f31d  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x18007f322  xor     r9d, r9d; nInBufferSize
0x18007f325  lea     rax, [rbp+OutBuffer]
0x18007f329  mov     [rsp+70h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18007f331  xor     r8d, r8d; lpInBuffer
0x18007f334  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x18007f339  mov     edx, 222014h; dwIoControlCode
0x18007f33e  mov     [rbp+OutBuffer], edi
0x18007f341  mov     rcx, r12; hDevice
0x18007f344  mov     [rbp+BytesReturned], edi
0x18007f347  call    cs:__imp_DeviceIoControl
0x18007f34d  test    eax, eax
0x18007f34f  jnz     short loc_18007F39C
0x18007f351  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f358  lea     rax, WPP_GLOBAL_Control
0x18007f35f  cmp     rcx, rax
0x18007f362  jz      loc_18007F53C
0x18007f368  cmp     byte ptr [rcx+19h], 2
0x18007f36c  jb      loc_18007F53C
0x18007f372  call    cs:__imp_GetLastError
0x18007f378  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f37f  mov     edx, 23h ; '#'
0x18007f384  mov     r9d, eax
0x18007f387  mov     rcx, [rcx+10h]
0x18007f38b  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f392  call    WPP_SF_d
0x18007f397  jmp     loc_18007F53C
0x18007f39c  mov     eax, [rbp+OutBuffer]
0x18007f39f  test    eax, eax
0x18007f3a1  jnz     short loc_18007F3DE
0x18007f3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f3aa  lea     rax, WPP_GLOBAL_Control
0x18007f3b1  cmp     rcx, rax
0x18007f3b4  jz      loc_18007F53C
0x18007f3ba  cmp     byte ptr [rcx+19h], 3
0x18007f3be  jb      loc_18007F53C
0x18007f3c4  mov     rcx, [rcx+10h]
0x18007f3c8  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f3cf  mov     edx, 24h ; '$'
0x18007f3d4  call    WPP_SF_
0x18007f3d9  jmp     loc_18007F53C
0x18007f3de  mov     ecx, eax
0x18007f3e0  mov     eax, 0E38h
0x18007f3e5  mul     rcx
0x18007f3e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007f3ef  cmovb   rax, r14
0x18007f3f3  mov     rcx, rax; unsigned __int64
0x18007f3f6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007f3fb  mov     rsi, rax
0x18007f3fe  test    rax, rax
0x18007f401  jz      loc_18007F573
0x18007f407  imul    eax, [rbp+OutBuffer], 0E38h
0x18007f40e  lea     rcx, [rbp+BytesReturned]
0x18007f412  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x18007f417  xor     r9d, r9d; nInBufferSize
0x18007f41a  mov     [rsp+70h+hTemplateFile], rcx; lpBytesReturned
0x18007f41f  xor     r8d, r8d; lpInBuffer
0x18007f422  mov     edx, 222018h; dwIoControlCode
0x18007f427  mov     rcx, r12; hDevice
0x18007f42a  mov     [rsp+70h+dwFlagsAndAttributes], eax; nOutBufferSize
0x18007f42e  mov     qword ptr [rsp+70h+dwCreationDisposition], rsi; lpOutBuffer
0x18007f433  call    cs:__imp_DeviceIoControl
0x18007f439  test    eax, eax
0x18007f43b  jnz     short loc_18007F488
0x18007f43d  call    cs:__imp_GetLastError
0x18007f443  mov     r9d, eax
0x18007f446  cmp     eax, 7Ah ; 'z'
0x18007f449  jnz     short loc_18007F45D
0x18007f44b  mov     rcx, rsi; Block
0x18007f44e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007f453  mov     eax, [rbp+OutBuffer]
0x18007f456  add     eax, eax
0x18007f458  mov     [rbp+OutBuffer], eax
0x18007f45b  jmp     short loc_18007F3DE
0x18007f45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f464  lea     rax, WPP_GLOBAL_Control
0x18007f46b  cmp     rcx, rax
0x18007f46e  jz      loc_18007F53C
0x18007f474  cmp     byte ptr [rcx+19h], 2
0x18007f478  jb      loc_18007F53C
0x18007f47e  mov     edx, 26h ; '&'
0x18007f483  jmp     loc_18007F387
0x18007f488  mov     ebx, [rbp+BytesReturned]
0x18007f48b  mov     rax, 2012012012012013h
0x18007f495  mul     rbx
0x18007f498  sub     rbx, rdx
0x18007f49b  shr     rbx, 1
0x18007f49e  add     rbx, rdx
0x18007f4a1  shr     rbx, 0Bh
0x18007f4a5  cmp     edi, ebx
0x18007f4a7  jnb     loc_18007F539
0x18007f4ad  mov     eax, edi
0x18007f4af  lea     r8, [rbp+var_18]; struct _GUID *
0x18007f4b3  imul    r15, rax, 0E38h
0x18007f4ba  xorps   xmm0, xmm0
0x18007f4bd  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18007f4c1  add     r15, rsi
0x18007f4c4  lea     r14, [r15+0D14h]
0x18007f4cb  mov     rdx, r14; wchar_t *
0x18007f4ce  call    ?ParseGuidFromDeviceString@VmSwitchNetSetupPlugin@@AEAA_NPEB_WAEAU_GUID@@@Z; VmSwitchNetSetupPlugin::ParseGuidFromDeviceString(wchar_t const *,_GUID &)
0x18007f4d3  test    al, al
0x18007f4d5  jz      short loc_18007F508
0x18007f4d7  mov     rax, qword ptr [rbp+var_18.Data1]
0x18007f4db  sub     rax, [r13+4]
0x18007f4df  jnz     short loc_18007F4E9
0x18007f4e1  mov     rax, qword ptr [rbp+var_18.Data4]
0x18007f4e5  sub     rax, [r13+0Ch]
0x18007f4e9  test    rax, rax
0x18007f4ec  jz      short loc_18007F4F2
0x18007f4ee  inc     edi
0x18007f4f0  jmp     short loc_18007F4A5
0x18007f4f2  mov     rcx, [rbp+var_28]; void *
0x18007f4f6  mov     rdx, r15; Src
0x18007f4f9  mov     r8d, 0E38h; Size
0x18007f4ff  call    memcpy_0
0x18007f504  mov     bl, 1
0x18007f506  jmp     short loc_18007F53C
0x18007f508  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f50f  lea     rax, WPP_GLOBAL_Control
0x18007f516  cmp     rcx, rax
0x18007f519  jz      short loc_18007F539
0x18007f51b  cmp     byte ptr [rcx+19h], 2
0x18007f51f  jb      short loc_18007F539
0x18007f521  mov     rcx, [rcx+10h]
0x18007f525  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007f52c  mov     edx, 27h ; '''
0x18007f531  mov     r9, r14
0x18007f534  call    WPP_SF_S
0x18007f539  mov     bl, [rbp+var_30]
0x18007f53c  mov     rcx, r12; hObject
0x18007f53f  call    cs:__imp_CloseHandle
0x18007f545  mov     rcx, rsi; Block
0x18007f548  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007f54d  mov     al, bl
0x18007f54f  mov     rcx, [rbp+var_8]
0x18007f553  xor     rcx, rsp; StackCookie
0x18007f556  call    __security_check_cookie
0x18007f55b  mov     rbx, [rsp+70h+arg_8]
0x18007f563  add     rsp, 70h
0x18007f567  pop     r15
0x18007f569  pop     r14
0x18007f56b  pop     r13
0x18007f56d  pop     r12
0x18007f56f  pop     rdi
0x18007f570  pop     rsi
0x18007f571  pop     rbp
0x18007f572  retn
0x18007f573  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f57a  lea     rax, WPP_GLOBAL_Control
0x18007f581  cmp     rcx, rax
0x18007f584  jz      short loc_18007F53C
0x18007f586  cmp     byte ptr [rcx+19h], 2
0x18007f58a  jb      short loc_18007F53C
0x18007f58c  mov     r9d, [rbp+OutBuffer]
0x18007f590  mov     edx, 25h ; '%'
0x18007f595  jmp     loc_18007F387
```
