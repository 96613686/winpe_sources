# RootHub_PopulatePortFlagsFromRegistry

- ea: `0x1400838a0`
- end: `0x140083aa1`
- name: `RootHub_PopulatePortFlagsFromRegistry`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14007eb90`

## callees

- `0x14001ad0c`
- `0x14001d02c`
- `0x14001f830`
- `0x1400599b0`
- `0x1400838a0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400839c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083969`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083969`

## pseudocode

```c
__int64 __fastcall RootHub_PopulatePortFlagsFromRegistry(__int64 a1)
{
  _QWORD *v1; // rdi
  __int64 result; // rax
  _UNKNOWN **v4; // rdx
  unsigned int v5; // r8d
  unsigned int Ulong; // eax
  _UNKNOWN **v7; // rdx
  _UNKNOWN **v8; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+10h] BYREF
  __int64 v11; // [rsp+68h] [rbp+18h] BYREF

  v1 = *(_QWORD **)(a1 + 8);
  v11 = 0;
  DestinationString = 0;
  v10 = 0;
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01033 + 384))(
             WdfDriverGlobals,
             *v1,
             1,
             131097,
             0,
             &v11);
  if ( (int)result >= 0 )
  {
    result = g_WdfDriverUsbXhciContext;
    if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) )
    {
      RtlInitUnicodeString(&DestinationString, L"IgnoreStatusChangesPortNumber");
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01033 + 1920))(
                 WdfDriverGlobals,
                 v11,
                 &DestinationString,
                 &v10);
      if ( (int)result >= 0 )
      {
        v5 = v10;
        if ( v10 <= *(_DWORD *)(a1 + 16)
          && v10
          && (result = *(_QWORD *)(a1 + 48), *(_BYTE *)(120LL * (v10 - 1) + result + 13) == 3) )
        {
          result = (__int64)KdDebuggerEnabled;
          if ( !(_BYTE)KdDebuggerEnabled
            || *(_BYTE *)(a1 + 56) == 1
            && (Ulong = XilRegister_ReadUlong(v1[11], (unsigned int *)(*(_QWORD *)(v1[11] + 72LL) + 36LL)),
                v5 = v10,
                result = HIBYTE(Ulong),
                (_DWORD)result != v10) )
          {
            result = *(_QWORD *)(a1 + 48);
            _InterlockedOr((volatile signed __int32 *)(120LL * (v5 - 1) + result + 64), 2u);
            v7 = &WPP_RECORDER_INITIALIZED;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v7) = 4;
              result = WPP_RECORDER_SF_D(
                         v1[9],
                         (_DWORD)v7,
                         11,
                         271,
                         (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                         v10);
            }
          }
        }
        else
        {
          v8 = &WPP_RECORDER_INITIALIZED;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v8) = 3;
            result = WPP_RECORDER_SF_D(
                       v1[9],
                       (_DWORD)v8,
                       4,
                       270,
                       (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                       v10);
          }
        }
      }
    }
  }
  else
  {
    v4 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 3;
      result = WPP_RECORDER_SF_d(
                 v1[9],
                 (_DWORD)v4,
                 11,
                 269,
                 (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids,
                 result);
    }
  }
  if ( v11 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01033 + 1848))(WdfDriverGlobals);
  return result;
}

```

## disassembly

```asm
0x1400838a0  mov     r11, rsp
0x1400838a3  mov     [r11+18h], rbx
0x1400838a7  mov     [r11+20h], rdi
0x1400838ab  push    rbp
0x1400838ac  mov     rbp, rsp
0x1400838af  sub     rsp, 50h
0x1400838b3  mov     rdi, [rcx+8]
0x1400838b7  mov     rbx, rcx
0x1400838ba  mov     rax, cs:WdfFunctions_01033
0x1400838c1  lea     rcx, [rbp+arg_8]
0x1400838c5  mov     [rbp+arg_8], 0
0x1400838cd  xorps   xmm0, xmm0
0x1400838d0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400838d4  mov     [rbp+arg_0], 0
0x1400838db  mov     r9d, 20019h
0x1400838e1  mov     rax, [rax+180h]
0x1400838e8  mov     r8d, 1
0x1400838ee  mov     rdx, [rdi]
0x1400838f1  mov     [r11-30h], rcx
0x1400838f5  mov     rcx, cs:WdfDriverGlobals
0x1400838fc  mov     qword ptr [r11-38h], 0
0x140083904  call    _guard_dispatch_icall
0x140083909  test    eax, eax
0x14008390b  jns     short loc_14008394D
0x14008390d  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083914  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14008391b  jz      loc_140083A6D
0x140083921  mov     rcx, [rdi+48h]
0x140083925  mov     r9d, 10Dh
0x14008392b  mov     [rsp+50h+var_28], eax
0x14008392f  mov     r8d, 0Bh
0x140083935  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x14008393c  mov     dl, 3
0x14008393e  mov     [rsp+50h+var_30], rax
0x140083943  call    WPP_RECORDER_SF_d
0x140083948  jmp     loc_140083A6D
0x14008394d  mov     rax, cs:g_WdfDriverUsbXhciContext
0x140083954  cmp     byte ptr [rax+1Ch], 0
0x140083958  jz      loc_140083A6D
0x14008395e  lea     rdx, aIgnorestatusch; "IgnoreStatusChangesPortNumber"
0x140083965  lea     rcx, [rbp+DestinationString]; DestinationString
0x140083969  call    cs:__imp_RtlInitUnicodeString
0x140083970  nop     dword ptr [rax+rax+00h]
0x140083975  mov     rax, cs:WdfFunctions_01033
0x14008397c  lea     r9, [rbp+arg_0]
0x140083980  mov     rdx, [rbp+arg_8]
0x140083984  lea     r8, [rbp+DestinationString]
0x140083988  mov     rcx, cs:WdfDriverGlobals
0x14008398f  mov     rax, [rax+780h]
0x140083996  call    _guard_dispatch_icall
0x14008399b  test    eax, eax
0x14008399d  js      loc_140083A6D
0x1400839a3  mov     r8d, [rbp+arg_0]
0x1400839a7  cmp     r8d, [rbx+10h]
0x1400839ab  ja      loc_140083A35
0x1400839b1  test    r8d, r8d
0x1400839b4  jz      short loc_140083A35
0x1400839b6  mov     rax, [rbx+30h]
0x1400839ba  lea     ecx, [r8-1]
0x1400839be  imul    rdx, rcx, 78h ; 'x'
0x1400839c2  cmp     byte ptr [rdx+rax+0Dh], 3
0x1400839c7  jnz     short loc_140083A35
0x1400839c9  mov     rax, cs:KdDebuggerEnabled
0x1400839d0  cmp     byte ptr [rax], 0
0x1400839d3  jz      short loc_1400839FC
0x1400839d5  cmp     byte ptr [rbx+38h], 1
0x1400839d9  jnz     loc_140083A6D
0x1400839df  mov     rcx, [rdi+58h]
0x1400839e3  mov     rdx, [rcx+48h]
0x1400839e7  add     rdx, 24h ; '$'
0x1400839eb  call    XilRegister_ReadUlong
0x1400839f0  mov     r8d, [rbp+arg_0]
0x1400839f4  shr     eax, 18h
0x1400839f7  cmp     eax, r8d
0x1400839fa  jz      short loc_140083A6D
0x1400839fc  mov     rax, [rbx+30h]
0x140083a00  lea     ecx, [r8-1]
0x140083a04  imul    rdx, rcx, 78h ; 'x'
0x140083a08  lock or dword ptr [rdx+rax+40h], 2
0x140083a0e  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083a15  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140083a1c  jz      short loc_140083A6D
0x140083a1e  mov     eax, [rbp+arg_0]
0x140083a21  mov     r9d, 10Fh
0x140083a27  mov     [rsp+50h+var_28], eax
0x140083a2b  mov     r8d, 0Bh
0x140083a31  mov     dl, 4
0x140083a33  jmp     short loc_140083A58
0x140083a35  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083a3c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140083a43  jz      short loc_140083A6D
0x140083a45  mov     [rsp+50h+var_28], r8d
0x140083a4a  mov     r9d, 10Eh
0x140083a50  mov     r8d, 4
0x140083a56  mov     dl, 3
0x140083a58  mov     rcx, [rdi+48h]
0x140083a5c  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140083a63  mov     [rsp+50h+var_30], rax
0x140083a68  call    WPP_RECORDER_SF_D
0x140083a6d  mov     rdx, [rbp+arg_8]
0x140083a71  test    rdx, rdx
0x140083a74  jz      short loc_140083A90
0x140083a76  mov     rax, cs:WdfFunctions_01033
0x140083a7d  mov     rcx, cs:WdfDriverGlobals
0x140083a84  mov     rax, [rax+738h]
0x140083a8b  call    _guard_dispatch_icall
0x140083a90  mov     rbx, [rsp+50h+arg_10]
0x140083a95  mov     rdi, [rsp+50h+arg_18]
0x140083a9a  add     rsp, 50h
0x140083a9e  pop     rbp
0x140083a9f  retn
```
