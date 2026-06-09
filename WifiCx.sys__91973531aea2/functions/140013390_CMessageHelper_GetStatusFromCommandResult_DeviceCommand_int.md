# CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)

- ea: `0x140013390`
- end: `0x140013500`
- name: `?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z`
- size: `368`
- prototype: `__int64 __fastcall(struct DeviceCommand *, int *)`
- caller_count: `13`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012cc0`
- `0x14004f700`
- `0x140062cb8`
- `0x140072050`
- `0x1400757c0`
- `0x140076f20`
- `0x14007c440`
- `0x140091df0`
- `0x140091f80`
- `0x1400ad970`
- `0x1400bb200`
- `0x1400be510`
- `0x1400c2760`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140013390`
- `0x140013510`
- `0x140024a20`

## pseudocode

```c
__int64 __fastcall CMessageHelper::GetStatusFromCommandResult(struct DeviceCommand *a1, unsigned int *a2)
{
  unsigned int CommandResult; // eax
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // ebx
  unsigned __int8 *v7; // r14
  int v8; // eax
  __int64 result; // rax
  unsigned int v10; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 *v11; // [rsp+70h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  CommandResult = DeviceCommand::get_CommandResult(a1, &v10, &v11);
  v6 = CommandResult;
  if ( CommandResult )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        13,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids,
        CommandResult);
    }
  }
  else if ( v10 >= 0x30 )
  {
    v7 = v11;
    v8 = *((_DWORD *)v11 + 5);
    if ( v8 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v5,
        15,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids,
        *(_DWORD *)v11,
        v8);
    }
    v6 = *((_DWORD *)v7 + 9);
    if ( v6 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v5,
        16,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids,
        *(_DWORD *)v7,
        *((_DWORD *)v7 + 9));
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        1,
        14,
        (__int64)WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids);
    }
    v6 = -1073676268;
  }
  result = v6;
  if ( a2 )
    *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x140013390  push    rbx
0x140013392  push    rsi
0x140013393  sub     rsp, 48h
0x140013397  xor     eax, eax
0x140013399  mov     [rsp+58h+arg_0], rbp
0x14001339e  mov     rsi, rdx
0x1400133a1  mov     [rsp+58h+arg_8], eax
0x1400133a5  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x1400133aa  mov     [rsp+58h+arg_10], rax
0x1400133af  lea     r8, [rsp+58h+arg_10]; unsigned __int8 **
0x1400133b4  mov     [rsp+58h+arg_18], rdi
0x1400133b9  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x1400133be  mov     ebx, eax
0x1400133c0  test    eax, eax
0x1400133c2  jz      short loc_14001340B
0x1400133c4  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400133cb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400133d2  jz      loc_1400134E5
0x1400133d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133df  lea     rbp, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x1400133e6  mov     [rsp+58h+var_30], eax
0x1400133ea  mov     r9d, 0Dh
0x1400133f0  mov     r8d, 1
0x1400133f6  mov     [rsp+58h+var_38], rbp
0x1400133fb  mov     dl, 2
0x1400133fd  mov     rcx, [rcx+40h]
0x140013401  call    WPP_RECORDER_SF_d
0x140013406  jmp     loc_1400134E5
0x14001340b  cmp     [rsp+58h+arg_8], 30h ; '0'
0x140013410  jnb     short loc_140013456
0x140013412  lea     rdi, WPP_RECORDER_INITIALIZED
0x140013419  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140013420  jz      short loc_14001344C
0x140013422  mov     rcx, cs:WPP_GLOBAL_Control
0x140013429  lea     rbp, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x140013430  mov     r9d, 0Eh
0x140013436  mov     [rsp+58h+var_38], rbp
0x14001343b  mov     r8d, 1
0x140013441  mov     dl, 2
0x140013443  mov     rcx, [rcx+40h]
0x140013447  call    WPP_RECORDER_SF_
0x14001344c  mov     ebx, 0C0010014h
0x140013451  jmp     loc_1400134E5
0x140013456  mov     [rsp+58h+var_18], r14
0x14001345b  lea     rbp, WPP_52dff22801773d96f6ef5b670d2cd017_Traceguids
0x140013462  mov     r14, [rsp+58h+arg_10]
0x140013467  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001346e  mov     eax, [r14+14h]
0x140013472  test    eax, eax
0x140013474  jz      short loc_1400134A7
0x140013476  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001347d  jz      short loc_1400134A7
0x14001347f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013486  mov     r9d, 0Fh
0x14001348c  mov     [rsp+58h+var_28], eax
0x140013490  mov     dl, 2
0x140013492  mov     eax, [r14]
0x140013495  mov     [rsp+58h+var_30], eax
0x140013499  mov     rcx, [rcx+40h]
0x14001349d  mov     [rsp+58h+var_38], rbp
0x1400134a2  call    WPP_RECORDER_SF_Ld
0x1400134a7  mov     ebx, [r14+24h]
0x1400134ab  test    ebx, ebx
0x1400134ad  jz      short loc_1400134E0
0x1400134af  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400134b6  jz      short loc_1400134E0
0x1400134b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134bf  mov     r9d, 10h
0x1400134c5  mov     eax, [r14]
0x1400134c8  mov     dl, 2
0x1400134ca  mov     [rsp+58h+var_28], ebx
0x1400134ce  mov     [rsp+58h+var_30], eax
0x1400134d2  mov     rcx, [rcx+40h]
0x1400134d6  mov     [rsp+58h+var_38], rbp
0x1400134db  call    WPP_RECORDER_SF_Ld
0x1400134e0  mov     r14, [rsp+58h+var_18]
0x1400134e5  mov     rdi, [rsp+58h+arg_18]
0x1400134ea  mov     eax, ebx
0x1400134ec  mov     rbp, [rsp+58h+arg_0]
0x1400134f1  test    rsi, rsi
0x1400134f4  jz      short loc_1400134F8
0x1400134f6  mov     [rsi], ebx
0x1400134f8  add     rsp, 48h
0x1400134fc  pop     rsi
0x1400134fd  pop     rbx
0x1400134fe  retn
```
