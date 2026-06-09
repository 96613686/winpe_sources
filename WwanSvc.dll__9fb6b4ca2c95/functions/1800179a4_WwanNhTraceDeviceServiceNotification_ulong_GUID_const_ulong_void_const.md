# WwanNhTraceDeviceServiceNotification(ulong,_GUID const *,ulong,void const *)

- ea: `0x1800179a4`
- end: `0x180017bc9`
- name: `?WwanNhTraceDeviceServiceNotification@@YAXKPEBU_GUID@@KPEBX@Z`
- size: `549`
- prototype: `void(unsigned int, const struct _GUID *, unsigned int, const void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018a34`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014080`
- `0x180014f1c`
- `0x1800179a4`
- `0x1800c5d28`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x180017a2c`
- `ntdll!RtlStringFromGUID` at `0x180017a2c`

## string_xrefs

- `0x180017ad2`: `[NH] Not supported: WwanNotificationSourceDeviceService\%s(%u)`
- `0x180017a7c`: `WwanNhTraceDeviceServiceNotification`
- `0x180017aa5`: `WwanNhTraceDeviceServiceNotification`
- `0x180017ad9`: `WwanNhTraceDeviceServiceNotification`
- `0x180017b45`: `WwanNhTraceDeviceServiceNotification`
- `0x180017b65`: `WwanNhTraceDeviceServiceNotification`
- `0x180017bb7`: `WwanNhTraceDeviceServiceNotification`
- `0x180017b4c`: `[NH] Dispatch: WwanNotificationSourceDeviceService\%s(%u)`
- `0x180017a75`: `[NH] Dispatch: WwanNotificationSourceDeviceService\%s(%u) - DeviceService GUID %s`
- `0x180017b70`: `[NH] HeaderSize mismatch: WwanNotificationSourceDeviceService\%s(%u)`
- `0x180017bac`: `[NH] Dispatch: WwanNotificationSourceDeviceService\%s(%u) - SessionId=%u`

## pseudocode

```c
void __fastcall WwanNhTraceDeviceServiceNotification(
        unsigned int a1,
        const struct _GUID *a2,
        unsigned int a3,
        char *a4)
{
  __int64 v4; // rbx
  __int64 v7; // rax
  const wchar_t *v8; // r9
  const wchar_t *v9; // r9
  int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+20h] [rbp-58h]
  _UNICODE_STRING GuidString; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF

  v4 = a1;
  if ( a1 > 8 )
  {
    if ( a1 != 9 && a1 != 10 && a1 != 11 )
    {
      if ( a1 == 12 || a1 == 13 )
        goto LABEL_10;
      if ( a1 == 14 )
        goto LABEL_25;
      if ( a1 != 15 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        return;
      }
      v9 = L"WwanDSEventTypeMax";
      v11 = 15;
      goto LABEL_15;
    }
  }
  else if ( a1 != 8 )
  {
    if ( a1 )
    {
      if ( a1 == 1 || a1 == 2 || a1 == 3 )
        goto LABEL_10;
      if ( a1 != 4 && a1 != 5 )
      {
        if ( a1 != 6 )
        {
LABEL_10:
          if ( a3 >= 0x28 )
          {
            GuidString = 0;
            RtlStringFromGUID((const GUID *const)(a4 + 8), &GuidString);
            memset(v13, 0, sizeof(v13));
            std::wstring::_Construct<1,unsigned short const *>(
              v13,
              GuidString.Buffer,
              (unsigned __int64)GuidString.Length >> 1);
            v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
            WwanLog::Info(
              "WwanNhTraceDeviceServiceNotification",
              a2,
              L"[NH] Dispatch: WwanNotificationSourceDeviceService\\%s(%u) - DeviceService GUID %s",
              off_1800CF440[v4],
              v4,
              v7);
            std::wstring::_Tidy_deallocate(v13);
            return;
          }
          v8 = off_1800CF440[a1];
          goto LABEL_28;
        }
        v8 = L"WwanDSEventTypeQueryInterfacesResponse";
        v10 = 6;
        if ( a3 < 0x18 )
        {
LABEL_29:
          WwanLog::Error(
            "WwanNhTraceDeviceServiceNotification",
            a2,
            L"[NH] HeaderSize mismatch: WwanNotificationSourceDeviceService\\%s(%u)",
            v8,
            v10);
          return;
        }
LABEL_26:
        WwanLog::Info(
          "WwanNhTraceDeviceServiceNotification",
          a2,
          L"[NH] Dispatch: WwanNotificationSourceDeviceService\\%s(%u)",
          v8,
          v10);
        return;
      }
LABEL_25:
      v10 = a1;
      v8 = off_1800CF440[a1];
      goto LABEL_26;
    }
    v9 = L"WwanDSEventTypeMin";
    v11 = 0;
LABEL_15:
    WwanLog::Error(
      "WwanNhTraceDeviceServiceNotification",
      a2,
      L"[NH] Not supported: WwanNotificationSourceDeviceService\\%s(%u)",
      v9,
      v11);
    return;
  }
  v8 = off_1800CF440[a1];
  if ( a3 < 0x14 )
  {
LABEL_28:
    v10 = a1;
    goto LABEL_29;
  }
  WwanLog::Info(
    "WwanNhTraceDeviceServiceNotification",
    a2,
    L"[NH] Dispatch: WwanNotificationSourceDeviceService\\%s(%u) - SessionId=%u",
    v8,
    a1,
    *((_DWORD *)a4 + 1));
}

```

## disassembly

```asm
0x1800179a4  mov     [rsp+arg_10], rbx
0x1800179a9  push    rdi
0x1800179aa  sub     rsp, 70h
0x1800179ae  mov     rax, cs:__security_cookie
0x1800179b5  xor     rax, rsp
0x1800179b8  mov     [rsp+78h+var_18], rax
0x1800179bd  mov     ebx, ecx
0x1800179bf  mov     r10, r9
0x1800179c2  mov     rdi, rdx
0x1800179c5  cmp     ecx, 8
0x1800179c8  ja      loc_180017AE5
0x1800179ce  jz      loc_180017B97
0x1800179d4  mov     eax, ebx
0x1800179d6  test    ecx, ecx
0x1800179d8  jz      loc_180017AC3
0x1800179de  sub     eax, 1
0x1800179e1  jz      short loc_180017A11
0x1800179e3  sub     eax, 1
0x1800179e6  jz      short loc_180017A11
0x1800179e8  sub     eax, 1
0x1800179eb  jz      short loc_180017A11
0x1800179ed  sub     eax, 1
0x1800179f0  jz      loc_180017B36
0x1800179f6  sub     eax, 1
0x1800179f9  jz      loc_180017B36
0x1800179ff  sub     eax, 1
0x180017a02  jz      loc_180017A9E
0x180017a08  cmp     eax, 1
0x180017a0b  jnz     loc_180017B1E
0x180017a11  cmp     r8d, 28h ; '('
0x180017a15  jb      loc_180017B5A
0x180017a1b  xorps   xmm0, xmm0
0x180017a1e  lea     rcx, [r9+8]; Guid
0x180017a22  lea     rdx, [rsp+78h+GuidString]; GuidString
0x180017a27  movups  xmmword ptr [rsp+78h+GuidString.Length], xmm0
0x180017a2c  call    cs:__imp_RtlStringFromGUID
0x180017a32  movzx   r8d, [rsp+78h+GuidString.Length]
0x180017a38  lea     rcx, [rsp+78h+var_38]
0x180017a3d  mov     rdx, [rsp+78h+GuidString.Buffer]
0x180017a42  xorps   xmm0, xmm0
0x180017a45  xorps   xmm1, xmm1
0x180017a48  shr     r8, 1
0x180017a4b  movups  [rsp+78h+var_38], xmm0
0x180017a50  movdqu  [rsp+78h+var_28], xmm1
0x180017a56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017a5b  lea     rcx, [rsp+78h+var_38]
0x180017a60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017a65  lea     rcx, off_1800CF440; "WwanDSEventTypeMin"
0x180017a6c  mov     [rsp+78h+var_50], rax
0x180017a71  mov     r9, [rcx+rbx*8]
0x180017a75  lea     r8, aNhDispatchWwan_9; "[NH] Dispatch: WwanNotificationSourceDe"...
0x180017a7c  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017a83  mov     [rsp+78h+var_58], ebx
0x180017a87  mov     rdx, rdi; struct _GUID *
0x180017a8a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180017a8f  lea     rcx, [rsp+78h+var_38]
0x180017a94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017a99  jmp     loc_180017B7C
0x180017a9e  mov     r9, cs:off_1800CF470; "WwanDSEventTypeQueryInterfacesResponse"
0x180017aa5  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017aac  mov     [rsp+78h+var_58], 6
0x180017ab4  cmp     r8d, 18h
0x180017ab8  jb      loc_180017B70
0x180017abe  jmp     loc_180017B4C
0x180017ac3  mov     r9, cs:off_1800CF440; "WwanDSEventTypeMin"
0x180017aca  mov     [rsp+78h+var_58], 0
0x180017ad2  lea     r8, aNhNotSupported; "[NH] Not supported: WwanNotificationSou"...
0x180017ad9  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017ae0  jmp     loc_180017B77
0x180017ae5  mov     eax, ebx
0x180017ae7  sub     eax, 9
0x180017aea  jz      loc_180017B97
0x180017af0  sub     eax, 1
0x180017af3  jz      loc_180017B97
0x180017af9  sub     eax, 1
0x180017afc  jz      loc_180017B97
0x180017b02  sub     eax, 1
0x180017b05  jz      loc_180017A11
0x180017b0b  sub     eax, 1
0x180017b0e  jz      loc_180017A11
0x180017b14  sub     eax, 1
0x180017b17  jz      short loc_180017B36
0x180017b19  cmp     eax, 1
0x180017b1c  jz      short loc_180017B25
0x180017b1e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017b23  jmp     short loc_180017B7C
0x180017b25  mov     r9, cs:off_1800CF4B8; "WwanDSEventTypeMax"
0x180017b2c  mov     [rsp+78h+var_58], 0Fh
0x180017b34  jmp     short loc_180017AD2
0x180017b36  lea     rcx, off_1800CF440; "WwanDSEventTypeMin"
0x180017b3d  mov     [rsp+78h+var_58], ebx
0x180017b41  mov     r9, [rcx+rbx*8]
0x180017b45  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017b4c  lea     r8, aNhDispatchWwan_10; "[NH] Dispatch: WwanNotificationSourceDe"...
0x180017b53  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180017b58  jmp     short loc_180017B7C
0x180017b5a  lea     rcx, off_1800CF440; "WwanDSEventTypeMin"
0x180017b61  mov     r9, [rcx+rbx*8]
0x180017b65  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017b6c  mov     [rsp+78h+var_58], ebx
0x180017b70  lea     r8, aNhHeadersizeMi; "[NH] HeaderSize mismatch: WwanNotificat"...
0x180017b77  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180017b7c  mov     rcx, [rsp+78h+var_18]
0x180017b81  xor     rcx, rsp; StackCookie
0x180017b84  call    __security_check_cookie
0x180017b89  mov     rbx, [rsp+78h+arg_10]
0x180017b91  add     rsp, 70h
0x180017b95  pop     rdi
0x180017b96  retn
0x180017b97  lea     rcx, off_1800CF440; "WwanDSEventTypeMin"
0x180017b9e  mov     r9, [rcx+rbx*8]
0x180017ba2  cmp     r8d, 14h
0x180017ba6  jb      short loc_180017B65
0x180017ba8  mov     eax, [r10+4]
0x180017bac  lea     r8, aNhDispatchWwan_49; "[NH] Dispatch: WwanNotificationSourceDe"...
0x180017bb3  mov     dword ptr [rsp+78h+var_50], eax
0x180017bb7  lea     rcx, aWwannhtracedev; "WwanNhTraceDeviceServiceNotification"
0x180017bbe  mov     [rsp+78h+var_58], ebx
0x180017bc2  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180017bc7  jmp     short loc_180017B7C
```
