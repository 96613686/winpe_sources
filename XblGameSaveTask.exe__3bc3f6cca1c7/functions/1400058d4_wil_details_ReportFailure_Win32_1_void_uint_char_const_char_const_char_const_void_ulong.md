# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x1400058d4`
- end: `0x140005936`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005fb0`

## callees

- `0x140002000`
- `0x140003de4`
- `0x1400058d4`

## string_xrefs

- `0x140005904`: `onecoreuap\xbox\ConnectedStorage\common\rpcclient.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-48h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v12[0] = v7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v12[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v9,
    v8,
    (int)"onecoreuap\\xbox\\ConnectedStorage\\common\\rpcclient.h",
    v9,
    v11,
    a6,
    (int)v12);
  return v7;
}

```

## disassembly

```asm
0x1400058d4  push    rbx
0x1400058d6  sub     rsp, 60h
0x1400058da  mov     ebx, dword ptr [rsp+68h+arg_30]
0x1400058e1  mov     r9, rcx
0x1400058e4  test    ebx, ebx
0x1400058e6  jle     short loc_1400058F1
0x1400058e8  movzx   ebx, bx
0x1400058eb  or      ebx, 80070000h
0x1400058f1  mov     ecx, ebx; this
0x1400058f3  mov     [rsp+68h+var_18], ebx
0x1400058f7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400058fc  mov     rcx, [rsp+68h+arg_28]
0x140005904  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\ConnectedStorage\\com"...
0x14000590b  mov     [rsp+68h+var_14], eax
0x14000590f  lea     rax, [rsp+68h+var_18]
0x140005914  mov     [rsp+68h+var_38], rax
0x140005919  mov     [rsp+68h+var_40], rcx
0x14000591e  mov     rcx, r9
0x140005921  mov     [rsp+68h+var_10], 0
0x140005929  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000592e  mov     eax, ebx
0x140005930  add     rsp, 60h
0x140005934  pop     rbx
0x140005935  retn
```
