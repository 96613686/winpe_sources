# KamDestroyTimer

- ea: `0x180003f00`
- end: `0x1800041f4`
- name: `KamDestroyTimer`
- size: `756`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005d70`
- `0x18000cae0`

## callees

- `0x180003ed0`
- `0x180003f00`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004192`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003f5c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003fa3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003f5c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003fa3`
- `TimeBrokerClient!TbDeleteEvent` at `0x180003f82`
- `TimeBrokerClient!TbDeleteEvent` at `0x180003f82`

## string_xrefs

- `0x180004077`: `Kam: TbDeleteEvent returned:`
- `0x1800041e3`: `Kam:KamDestroyTimer failed to impersonate`

## pseudocode

```c
__int64 __fastcall KamDestroyTimer(__int64 a1)
{
  PVOID *v2; // rcx
  __int64 v3; // rcx
  unsigned int v4; // eax
  PVOID v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // edi
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // [rsp+30h] [rbp-68h] BYREF
  __int128 v19; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-48h] BYREF
  const wchar_t *v21; // [rsp+60h] [rbp-38h]
  __int64 v22; // [rsp+68h] [rbp-30h]
  int *v23; // [rsp+70h] [rbp-28h]
  __int64 v24; // [rsp+78h] [rbp-20h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_BYTE *)(a1 + 361) )
  {
    if ( SetThreadToken(0, *(HANDLE *)(a1 + 224)) )
    {
      v3 = *(_QWORD *)(a1 + 240);
      v19 = *(_OWORD *)(a1 + 308);
      v4 = TbDeleteEvent(v3, &v19);
      v7 = v4;
      if ( v4 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v4);
        }
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        v18 = v7;
        v21 = L"Kam: TbDeleteEvent returned:";
        v22 = 58;
        v23 = (int *)&v18;
        v24 = 4;
        McGenEventWrite_EventWriteTransfer(v5, NcbApiStatus, v6, 3, v20);
      }
      if ( SetThreadToken(0, 0) )
        goto LABEL_8;
      LastError = GetLastError();
      v12 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v17, v16, L"Kam:KamDestroyTimer failed to revert", LastError);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_8;
      }
      v14 = 82;
    }
    else
    {
      v9 = GetLastError();
      v12 = v9;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, v10, L"Kam:KamDestroyTimer failed to impersonate", v9);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_8;
      }
      v14 = 83;
    }
    WPP_SF_d(v13[2], v14, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v12);
LABEL_8:
    *(_BYTE *)(a1 + 361) = 0;
LABEL_9:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
  {
    WPP_SF_(v2[2], 84, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( *(_QWORD *)(a1 + 384) )
  {
    VpnFree(*(LPVOID *)(a1 + 384));
    *(_QWORD *)(a1 + 384) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 85, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180003f00  mov     r11, rsp
0x180003f03  sub     rsp, 98h
0x180003f0a  mov     rax, cs:__security_cookie
0x180003f11  xor     rax, rsp
0x180003f14  mov     [rsp+98h+var_18], rax
0x180003f1c  mov     [r11+10h], rbx
0x180003f20  mov     rbx, rcx
0x180003f23  mov     [r11+18h], rsi
0x180003f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f2e  lea     rsi, WPP_GLOBAL_Control
0x180003f35  cmp     rcx, rsi
0x180003f38  jnz     loc_180004042
0x180003f3e  cmp     byte ptr [rbx+169h], 0
0x180003f45  jz      loc_1800040C4
0x180003f4b  mov     rdx, [rbx+0E0h]; Token
0x180003f52  xor     ecx, ecx; Thread
0x180003f54  mov     [rsp+98h+var_8], rdi
0x180003f5c  call    cs:__imp_SetThreadToken
0x180003f62  test    eax, eax
0x180003f64  jz      loc_1800040FB
0x180003f6a  movups  xmm0, xmmword ptr [rbx+134h]
0x180003f71  mov     rcx, [rbx+0F0h]
0x180003f78  lea     rdx, [rsp+98h+var_58]
0x180003f7d  movaps  [rsp+98h+var_58], xmm0
0x180003f82  call    cs:__imp_TbDeleteEvent
0x180003f88  mov     edi, eax
0x180003f8a  test    eax, eax
0x180003f8c  jnz     loc_180004151
0x180003f92  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180003f99  jnz     loc_180004077
0x180003f9f  xor     edx, edx; Token
0x180003fa1  xor     ecx, ecx; Thread
0x180003fa3  call    cs:__imp_SetThreadToken
0x180003fa9  test    eax, eax
0x180003fab  jz      loc_180004192
0x180003fb1  mov     rdi, [rsp+98h+var_8]
0x180003fb9  mov     byte ptr [rbx+169h], 0
0x180003fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fc7  mov     rax, [rbx+180h]
0x180003fce  test    rax, rax
0x180003fd1  jz      short loc_180003FED
0x180003fd3  mov     rcx, rax; lpMem
0x180003fd6  call    VpnFree
0x180003fdb  mov     qword ptr [rbx+180h], 0
0x180003fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fed  mov     rbx, [rsp+98h+arg_8]
0x180003ff5  cmp     rcx, rsi
0x180003ff8  mov     rsi, [rsp+98h+arg_10]
0x180004000  jnz     short loc_18000401C
0x180004002  xor     eax, eax
0x180004004  mov     rcx, [rsp+98h+var_18]
0x18000400c  xor     rcx, rsp; StackCookie
0x18000400f  call    __security_check_cookie
0x180004014  add     rsp, 98h
0x18000401b  retn
0x18000401c  test    byte ptr [rcx+1Ch], 1
0x180004020  jz      short loc_180004002
0x180004022  cmp     byte ptr [rcx+19h], 6
0x180004026  jb      short loc_180004002
0x180004028  mov     rcx, [rcx+10h]
0x18000402c  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180004033  mov     edx, 55h ; 'U'
0x180004038  xor     r9d, r9d
0x18000403b  call    WPP_SF_d
0x180004040  jmp     short loc_180004002
0x180004042  test    byte ptr [rcx+1Ch], 1
0x180004046  jz      loc_180003F3E
0x18000404c  cmp     byte ptr [rcx+19h], 6
0x180004050  jb      loc_180003F3E
0x180004056  mov     rcx, [rcx+10h]
0x18000405a  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180004061  mov     edx, 50h ; 'P'
0x180004066  call    WPP_SF_
0x18000406b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004072  jmp     loc_180003F3E
0x180004077  lea     rax, aKamTbdeleteeve; "Kam: TbDeleteEvent returned:"
0x18000407e  mov     [rsp+98h+var_68], edi
0x180004082  mov     [rsp+98h+var_38], rax
0x180004087  lea     rdx, NcbApiStatus
0x18000408e  lea     rax, [rsp+98h+var_68]
0x180004093  mov     [rsp+98h+var_30], 3Ah ; ':'
0x18000409c  mov     [rsp+98h+var_28], rax
0x1800040a1  mov     r9d, 3
0x1800040a7  lea     rax, [rsp+98h+var_48]
0x1800040ac  mov     [rsp+98h+var_20], 4
0x1800040b5  mov     [rsp+98h+var_78], rax
0x1800040ba  call    McGenEventWrite_EventWriteTransfer
0x1800040bf  jmp     loc_180003F9F
0x1800040c4  cmp     rcx, rsi
0x1800040c7  jz      loc_180003FC7
0x1800040cd  test    byte ptr [rcx+1Ch], 1
0x1800040d1  jz      loc_180003FC7
0x1800040d7  cmp     byte ptr [rcx+19h], 5
0x1800040db  jb      loc_180003FC7
0x1800040e1  mov     rcx, [rcx+10h]
0x1800040e5  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800040ec  mov     edx, 54h ; 'T'
0x1800040f1  call    WPP_SF_
0x1800040f6  jmp     loc_180003FC0
0x1800040fb  call    cs:__imp_GetLastError
0x180004101  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004108  mov     edi, eax
0x18000410a  jnz     loc_1800041E0
0x180004110  mov     rcx, cs:WPP_GLOBAL_Control
0x180004117  cmp     rcx, rsi
0x18000411a  jz      loc_180003FB1
0x180004120  test    byte ptr [rcx+1Ch], 1
0x180004124  jz      loc_180003FB1
0x18000412a  cmp     byte ptr [rcx+19h], 2
0x18000412e  jb      loc_180003FB1
0x180004134  mov     edx, 53h ; 'S'
0x180004139  mov     rcx, [rcx+10h]
0x18000413d  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180004144  mov     r9d, edi
0x180004147  call    WPP_SF_d
0x18000414c  jmp     loc_180003FB1
0x180004151  mov     rcx, cs:WPP_GLOBAL_Control
0x180004158  cmp     rcx, rsi
0x18000415b  jz      loc_180003F92
0x180004161  test    byte ptr [rcx+1Ch], 1
0x180004165  jz      loc_180003F92
0x18000416b  cmp     byte ptr [rcx+19h], 3
0x18000416f  jb      loc_180003F92
0x180004175  mov     rcx, [rcx+10h]
0x180004179  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180004180  mov     edx, 51h ; 'Q'
0x180004185  mov     r9d, edi
0x180004188  call    WPP_SF_d
0x18000418d  jmp     loc_180003F92
0x180004192  call    cs:__imp_GetLastError
0x180004198  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000419f  mov     edi, eax
0x1800041a1  jz      short loc_1800041B2
0x1800041a3  mov     r9d, eax
0x1800041a6  lea     r8, aKamKamdestroyt; "Kam:KamDestroyTimer failed to revert"
0x1800041ad  call    McTemplateU0zq_EventWriteTransfer
0x1800041b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041b9  cmp     rcx, rsi
0x1800041bc  jz      loc_180003FB1
0x1800041c2  test    byte ptr [rcx+1Ch], 1
0x1800041c6  jz      loc_180003FB1
0x1800041cc  cmp     byte ptr [rcx+19h], 2
0x1800041d0  jb      loc_180003FB1
0x1800041d6  mov     edx, 52h ; 'R'
0x1800041db  jmp     loc_180004139
0x1800041e0  mov     r9d, edi
0x1800041e3  lea     r8, aKamKamdestroyt_0; "Kam:KamDestroyTimer failed to impersona"...
0x1800041ea  call    McTemplateU0zq_EventWriteTransfer
0x1800041ef  jmp     loc_180004110
```
