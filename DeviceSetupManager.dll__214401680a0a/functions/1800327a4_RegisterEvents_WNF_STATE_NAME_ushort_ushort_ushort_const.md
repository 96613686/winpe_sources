# _RegisterEvents(_WNF_STATE_NAME,ushort *,ushort *,ushort const *)

- ea: `0x1800327a4`
- end: `0x1800329d8`
- name: `?_RegisterEvents@@YAJU_WNF_STATE_NAME@@PEAG1PEBG@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031a84`

## callees

- `0x18001af70`
- `0x180027ba8`
- `0x18003187c`
- `0x180032338`
- `0x180032438`
- `0x180032630`
- `0x1800327a4`
- `0x180032c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800329b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800329b0`
- `ntdll!RtlInitUnicodeString` at `0x18003290b`
- `ntdll!RtlInitUnicodeString` at `0x180032919`
- `ntdll!RtlInitUnicodeString` at `0x18003290b`
- `ntdll!RtlInitUnicodeString` at `0x180032919`
- `SystemEventsBrokerClient!SebRegisterPrivateEvent` at `0x180032881`
- `SystemEventsBrokerClient!SebRegisterPrivateEvent` at `0x180032881`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationExtensionClass` at `0x180032941`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationExtensionClass` at `0x180032941`

## pseudocode

```c
__int64 __fastcall _RegisterEvents(
        struct _WNF_STATE_NAME a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v5; // rsi
  int v8; // r15d
  unsigned int v9; // r14d
  int v10; // r8d
  int v11; // eax
  WCHAR *v12; // rbx
  int v13; // ecx
  __int64 v14; // rax
  unsigned int v16; // [rsp+40h] [rbp-39h] BYREF
  PCWSTR v17; // [rsp+48h] [rbp-31h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-29h] BYREF
  struct _UNICODE_STRING v19; // [rsp+58h] [rbp-21h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  __int128 v21; // [rsp+78h] [rbp-1h] BYREF
  __int128 v22; // [rsp+88h] [rbp+Fh] BYREF

  v5 = a3;
  SourceString = (PCWSTR)a1;
  v16 = 0;
  v17 = 0;
  v8 = _EventTypeFromIDAssetPair(a3, (enum _SebiEventType *)&v16, (unsigned __int16 **)&v17);
  if ( v8 >= 0 )
  {
    v9 = v16;
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))_IsEventRegistered)(a2, a1, v16, a4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_LLSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v10, a1.Data[0], SBYTE4(SourceString), (__int64)a2, v9);
      v21 = 0;
      v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))SebRegisterPrivateEvent)(
             a1,
             a2,
             &v21,
             0,
             v9,
             0,
             1);
      v16 = v8;
      if ( v8 >= 0 && *v5 )
      {
        do
        {
          v22 = 0;
          SourceString = 0;
          v11 = _ExtensionClassFromIDAssetPair(v5, (unsigned __int16 **)&SourceString);
          v12 = (WCHAR *)SourceString;
          if ( v11 >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                12,
                &WPP_d57ca44452473f5574b7c550b191f620_Traceguids,
                SourceString);
            DestinationString = 0;
            v19 = 0;
            RtlInitUnicodeString(&DestinationString, v12);
            RtlInitUnicodeString(&v19, v17);
            if ( (int)BiPtAssociateApplicationExtensionClass(&v22, &DestinationString, &v21, 0, 0, 0, &v19) >= 0
              && (Microsoft_Windows_DeviceSetupManagerEnableBits & 0x40) != 0 )
            {
              McTemplateU0zzz_EventWriteTransfer(
                v13,
                (unsigned int)DsmRegisteredBackgroundTask,
                (_DWORD)a4,
                (_DWORD)a2,
                (__int64)v5);
            }
          }
          if ( v12 )
            CoTaskMemFree(v12);
          v14 = -1;
          do
            ++v14;
          while ( v5[v14] );
          v5 += v14 + 1;
        }
        while ( *v5 );
        v8 = v16;
      }
    }
  }
  if ( v17 )
    CoTaskMemFree((LPVOID)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800327a4  push    rbp
0x1800327a6  push    rbx
0x1800327a7  push    rsi
0x1800327a8  push    r12
0x1800327aa  push    r13
0x1800327ac  push    r14
0x1800327ae  push    r15
0x1800327b0  lea     rbp, [rsp-27h]
0x1800327b5  sub     rsp, 0A0h
0x1800327bc  mov     rax, cs:__security_cookie
0x1800327c3  xor     rax, rsp
0x1800327c6  mov     [rbp+57h+var_38], rax
0x1800327ca  mov     r13, r9
0x1800327cd  mov     rsi, r8
0x1800327d0  mov     r12, rdx
0x1800327d3  mov     rbx, rcx
0x1800327d6  mov     [rbp+57h+SourceString], rcx
0x1800327da  xor     r14d, r14d
0x1800327dd  mov     [rbp+57h+var_90], r14d
0x1800327e1  mov     [rbp+57h+var_88], r14
0x1800327e5  lea     r8, [rbp+57h+var_88]; unsigned __int16 **
0x1800327e9  lea     rdx, [rbp+57h+var_90]; enum _SebiEventType *
0x1800327ed  mov     rcx, rsi; unsigned __int16 *
0x1800327f0  call    ?_EventTypeFromIDAssetPair@@YAJPEBGPEAW4_SebiEventType@@PEAPEAG@Z; _EventTypeFromIDAssetPair(ushort const *,_SebiEventType *,ushort * *)
0x1800327f5  mov     r15d, eax
0x1800327f8  test    eax, eax
0x1800327fa  js      loc_1800329A6
0x180032800  mov     r9, r13
0x180032803  mov     r14d, [rbp+57h+var_90]
0x180032807  mov     r8d, r14d
0x18003280a  mov     rdx, rbx
0x18003280d  mov     rcx, r12
0x180032810  call    ?_IsEventRegistered@@YA_NPEAGU_WNF_STATE_NAME@@W4_SebiEventType@@PEBG@Z; _IsEventRegistered(ushort *,_WNF_STATE_NAME,_SebiEventType,ushort const *)
0x180032815  test    al, al
0x180032817  jnz     loc_1800329A3
0x18003281d  lea     rax, WPP_GLOBAL_Control
0x180032824  mov     rcx, cs:WPP_GLOBAL_Control
0x18003282b  cmp     rcx, rax
0x18003282e  jz      short loc_180032858
0x180032830  test    byte ptr [rcx+1Ch], 1
0x180032834  jz      short loc_180032858
0x180032836  mov     edx, 0Bh
0x18003283b  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x180032840  mov     [rsp+0D0h+var_A8], r12
0x180032845  mov     eax, dword ptr [rbp+57h+SourceString+4]
0x180032848  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18003284c  mov     r9d, ebx
0x18003284f  mov     rcx, [rcx+10h]
0x180032853  call    WPP_SF_LLSD
0x180032858  xorps   xmm0, xmm0
0x18003285b  movups  [rbp+57h+var_58], xmm0
0x18003285f  mov     dword ptr [rsp+0D0h+var_A0], 1
0x180032867  mov     dword ptr [rsp+0D0h+var_A8], 0
0x18003286f  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180032874  xor     r9d, r9d
0x180032877  lea     r8, [rbp+57h+var_58]
0x18003287b  mov     rdx, r12
0x18003287e  mov     rcx, rbx
0x180032881  call    cs:__imp_SebRegisterPrivateEvent
0x180032887  mov     r15d, eax
0x18003288a  mov     [rbp+57h+var_90], eax
0x18003288d  xor     r14d, r14d
0x180032890  test    eax, eax
0x180032892  js      loc_1800329A6
0x180032898  cmp     [rsi], r14w
0x18003289c  jz      loc_1800329A6
0x1800328a2  lea     r15, WPP_GLOBAL_Control
0x1800328a9  xorps   xmm0, xmm0
0x1800328ac  movups  [rbp+57h+var_48], xmm0
0x1800328b0  mov     [rbp+57h+SourceString], r14
0x1800328b4  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x1800328b8  mov     rcx, rsi; unsigned __int16 *
0x1800328bb  call    ?_ExtensionClassFromIDAssetPair@@YAJPEBGPEAPEAG@Z; _ExtensionClassFromIDAssetPair(ushort const *,ushort * *)
0x1800328c0  mov     rbx, [rbp+57h+SourceString]
0x1800328c4  test    eax, eax
0x1800328c6  js      loc_18003296F
0x1800328cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328d3  cmp     rcx, r15
0x1800328d6  jz      short loc_1800328F6
0x1800328d8  test    byte ptr [rcx+1Ch], 1
0x1800328dc  jz      short loc_1800328F6
0x1800328de  mov     edx, 0Ch
0x1800328e3  mov     r9, rbx
0x1800328e6  lea     r8, WPP_d57ca44452473f5574b7c550b191f620_Traceguids
0x1800328ed  mov     rcx, [rcx+10h]
0x1800328f1  call    WPP_SF_S
0x1800328f6  xorps   xmm0, xmm0
0x1800328f9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800328fd  xorps   xmm1, xmm1
0x180032900  movups  xmmword ptr [rbp+57h+var_78.Length], xmm1
0x180032904  mov     rdx, rbx; SourceString
0x180032907  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003290b  call    cs:__imp_RtlInitUnicodeString
0x180032911  mov     rdx, [rbp+57h+var_88]; SourceString
0x180032915  lea     rcx, [rbp+57h+var_78]; DestinationString
0x180032919  call    cs:__imp_RtlInitUnicodeString
0x18003291f  lea     rax, [rbp+57h+var_78]
0x180032923  mov     [rsp+0D0h+var_A0], rax
0x180032928  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x18003292d  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180032932  xor     r9d, r9d
0x180032935  lea     r8, [rbp+57h+var_58]
0x180032939  lea     rdx, [rbp+57h+DestinationString]
0x18003293d  lea     rcx, [rbp+57h+var_48]
0x180032941  call    cs:__imp_BiPtAssociateApplicationExtensionClass
0x180032947  or      eax, 10000000h
0x18003294c  jl      short loc_18003296F
0x18003294e  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 40h
0x180032955  jz      short loc_18003296F
0x180032957  mov     [rsp+0D0h+var_B0], rsi
0x18003295c  mov     r9, r12
0x18003295f  mov     r8, r13
0x180032962  lea     rdx, DsmRegisteredBackgroundTask
0x180032969  call    McTemplateU0zzz_EventWriteTransfer
0x18003296e  nop
0x18003296f  test    rbx, rbx
0x180032972  jz      short loc_18003297D
0x180032974  mov     rcx, rbx; pv
0x180032977  call    cs:__imp_CoTaskMemFree
0x18003297d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032981  inc     rax
0x180032984  cmp     [rsi+rax*2], r14w
0x180032989  jnz     short loc_180032981
0x18003298b  lea     rsi, [rsi+rax*2]
0x18003298f  add     rsi, 2
0x180032993  cmp     [rsi], r14w
0x180032997  jnz     loc_1800328A9
0x18003299d  mov     r15d, [rbp+57h+var_90]
0x1800329a1  jmp     short loc_1800329A6
0x1800329a3  xor     r14d, r14d
0x1800329a6  cmp     [rbp+57h+var_88], r14
0x1800329aa  jz      short loc_1800329B6
0x1800329ac  mov     rcx, [rbp+57h+var_88]; pv
0x1800329b0  call    cs:__imp_CoTaskMemFree
0x1800329b6  mov     eax, r15d
0x1800329b9  mov     rcx, [rbp+57h+var_38]
0x1800329bd  xor     rcx, rsp; StackCookie
0x1800329c0  call    __security_check_cookie
0x1800329c5  add     rsp, 0A0h
0x1800329cc  pop     r15
0x1800329ce  pop     r14
0x1800329d0  pop     r13
0x1800329d2  pop     r12
0x1800329d4  pop     rsi
0x1800329d5  pop     rbx
0x1800329d6  pop     rbp
0x1800329d7  retn
```
