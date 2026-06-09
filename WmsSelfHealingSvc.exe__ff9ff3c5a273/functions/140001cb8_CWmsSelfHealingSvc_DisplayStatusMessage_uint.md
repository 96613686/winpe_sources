# CWmsSelfHealingSvc::DisplayStatusMessage(uint)

- ea: `0x140001cb8`
- end: `0x140001e26`
- name: `?DisplayStatusMessage@CWmsSelfHealingSvc@@AEAAJI@Z`
- size: `366`
- prototype: `__int64 __fastcall(CWmsSelfHealingSvc *this, UINT)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400029e8`
- `0x140002c94`

## callees

- `0x140001cb8`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140008710`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140001e09`
- `KERNEL32!FreeLibrary` at `0x140001e09`
- `KERNEL32!IsDebuggerPresent` at `0x140001d76`
- `KERNEL32!IsDebuggerPresent` at `0x140001d76`
- `KERNEL32!GetLastError` at `0x140001d20`
- `KERNEL32!GetLastError` at `0x140001d20`
- `USER32!LoadStringW` at `0x140001d12`
- `USER32!LoadStringW` at `0x140001d12`
- `WMsgAPI!WmsgPostNotifyMessage` at `0x140001de8`
- `WMsgAPI!WmsgPostNotifyMessage` at `0x140001de8`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::DisplayStatusMessage(CWmsSelfHealingSvc *this, UINT a2)
{
  const unsigned __int16 *v3; // rdx
  signed int v4; // ebx
  signed int LastError; // eax
  unsigned int v6; // eax
  signed int v8; // [rsp+30h] [rbp-28h]
  signed int v9; // [rsp+38h] [rbp-20h]
  HINSTANCE hInstance; // [rsp+60h] [rbp+8h] BYREF
  __int64 Buffer; // [rsp+70h] [rbp+18h] BYREF

  hInstance = 0;
  Buffer = 0;
  DEBUGMSG(L"CWmsSelfHealingSvc::DisplayStatusMessage\n");
  v4 = LoadResourceDLL(&hInstance, v3);
  if ( v4 >= 0 )
  {
    if ( LoadStringW(hInstance, a2, (LPWSTR)&Buffer, 0) )
    {
      v6 = WmsgPostNotifyMessage(0, 768, 0, Buffer);
      DEBUGMSG(L"CWmsSelfHealingSvc::DisplayStatusMessage - WmsgPostNotifyMessage returned 0x%X\n", v6);
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        0x14Cu,
        L"CWmsSelfHealingSvc::DisplayStatusMessage",
        L"CBRAEx",
        L"cchStatusMessage != 0",
        v4);
      if ( IsDebuggerPresent() )
      {
        v9 = v4;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
          332,
          L"CWmsSelfHealingSvc::DisplayStatusMessage",
          L"CBRAEx",
          L"cchStatusMessage != 0",
          v9);
      }
      else
      {
        v8 = v4;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
          332,
          L"CWmsSelfHealingSvc::DisplayStatusMessage",
          L"CBRAEx",
          L"cchStatusMessage != 0",
          v8);
      }
    }
  }
  if ( hInstance )
    FreeLibrary(hInstance);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140001cb8  mov     rax, rsp
0x140001cbb  mov     [rax+10h], rbx
0x140001cbf  mov     [rax+20h], rsi
0x140001cc3  mov     [rax+8], rcx
0x140001cc7  push    r12
0x140001cc9  push    r14
0x140001ccb  push    r15
0x140001ccd  sub     rsp, 40h
0x140001cd1  lea     rcx, aCwmsselfhealin_22; "CWmsSelfHealingSvc::DisplayStatusMessag"...
0x140001cd8  mov     qword ptr [rax+8], 0
0x140001ce0  mov     esi, edx
0x140001ce2  mov     qword ptr [rax+18h], 0
0x140001cea  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140001cef  lea     rcx, [rsp+58h+hInstance]; HINSTANCE *
0x140001cf4  call    ?LoadResourceDLL@@YAJPEAPEAUHINSTANCE__@@PEBG@Z; LoadResourceDLL(HINSTANCE__ * *,ushort const *)
0x140001cf9  mov     ebx, eax
0x140001cfb  test    eax, eax
0x140001cfd  js      loc_140001DFC
0x140001d03  mov     rcx, [rsp+58h+hInstance]; hInstance
0x140001d08  lea     r8, [rsp+58h+Buffer]; lpBuffer
0x140001d0d  xor     r9d, r9d; cchBufferMax
0x140001d10  mov     edx, esi; uID
0x140001d12  call    cs:__imp_LoadStringW
0x140001d18  test    eax, eax
0x140001d1a  jnz     loc_140001DD9
0x140001d20  call    cs:__imp_GetLastError
0x140001d26  mov     ebx, eax
0x140001d28  test    eax, eax
0x140001d2a  jle     short loc_140001D35
0x140001d2c  movzx   ebx, ax
0x140001d2f  or      ebx, 80070000h
0x140001d35  mov     eax, 80004005h
0x140001d3a  lea     r12, aCbraex; "CBRAEx"
0x140001d41  test    ebx, ebx
0x140001d43  lea     r14, aCwmsselfhealin_30; "CWmsSelfHealingSvc::DisplayStatusMessag"...
0x140001d4a  mov     esi, 14Ch
0x140001d4f  lea     r15, aCchstatusmessa; "cchStatusMessage != 0"
0x140001d56  cmovns  ebx, eax
0x140001d59  lea     rcx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140001d60  mov     [rsp+58h+var_30], ebx; int
0x140001d64  mov     r9, r12; unsigned __int16 *
0x140001d67  mov     r8, r14; unsigned __int16 *
0x140001d6a  mov     [rsp+58h+var_38], r15; unsigned __int16 *
0x140001d6f  mov     edx, esi; unsigned int
0x140001d71  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140001d76  call    cs:__imp_IsDebuggerPresent
0x140001d7c  test    eax, eax
0x140001d7e  jz      short loc_140001DB0
0x140001d80  mov     [rsp+58h+var_20], ebx
0x140001d84  lea     r8, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140001d8b  mov     [rsp+58h+var_28], r15
0x140001d90  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140001d97  mov     qword ptr [rsp+58h+var_30], r12
0x140001d9c  mov     r9d, esi
0x140001d9f  mov     ecx, 2; unsigned __int8
0x140001da4  mov     [rsp+58h+var_38], r14
0x140001da9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140001dae  jmp     short loc_140001DFC
0x140001db0  mov     dword ptr [rsp+58h+var_28], ebx
0x140001db4  lea     rdx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140001dbb  mov     qword ptr [rsp+58h+var_30], r15
0x140001dc0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140001dc7  mov     r9, r14
0x140001dca  mov     [rsp+58h+var_38], r12
0x140001dcf  mov     r8d, esi
0x140001dd2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140001dd7  jmp     short loc_140001DFC
0x140001dd9  mov     r9, [rsp+58h+Buffer]
0x140001dde  xor     r8d, r8d
0x140001de1  mov     edx, 300h
0x140001de6  xor     ecx, ecx
0x140001de8  call    cs:__imp_WmsgPostNotifyMessage
0x140001dee  mov     edx, eax
0x140001df0  lea     rcx, aCwmsselfhealin_21; "CWmsSelfHealingSvc::DisplayStatusMessag"...
0x140001df7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140001dfc  cmp     [rsp+58h+hInstance], 0
0x140001e02  jz      short loc_140001E0F
0x140001e04  mov     rcx, [rsp+58h+hInstance]; hLibModule
0x140001e09  call    cs:__imp_FreeLibrary
0x140001e0f  mov     rsi, [rsp+58h+arg_18]
0x140001e14  mov     eax, ebx
0x140001e16  mov     rbx, [rsp+58h+arg_8]
0x140001e1b  add     rsp, 40h
0x140001e1f  pop     r15
0x140001e21  pop     r14
0x140001e23  pop     r12
0x140001e25  retn
```
