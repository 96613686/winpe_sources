# AccessCheck(void *)

- ea: `0x1800063c8`
- end: `0x1800064f1`
- name: `?AccessCheck@@YA_NPEAX@Z`
- size: `297`
- prototype: `char __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180006500`

## callees

- `0x180006140`
- `0x1800061ac`
- `0x1800063c8`
- `0x180006740`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800063e4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800063e4`
- `RPCRT4!RpcImpersonateClient` at `0x180006445`
- `RPCRT4!RpcImpersonateClient` at `0x180006445`
- `RPCRT4!RpcRevertToSelf` at `0x1800064de`
- `RPCRT4!RpcRevertToSelf` at `0x1800064de`

## pseudocode

```c
char __fastcall AccessCheck(RPC_BINDING_HANDLE BindingHandle)
{
  char v2; // bl
  int v3; // eax
  _QWORD *v4; // r10
  __int64 v5; // rdx
  unsigned int Pid; // [rsp+38h] [rbp+10h] BYREF
  struct _APF_APP_INFO *v8; // [rsp+40h] [rbp+18h] BYREF

  Pid = 0;
  v2 = 0;
  v3 = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
  if ( v3 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 18;
LABEL_8:
      WPP_SF_d(v4[2], v5, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids, (unsigned int)v3);
    }
  }
  else
  {
    v3 = RpcImpersonateClient(BindingHandle);
    if ( v3 )
    {
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 19;
        goto LABEL_8;
      }
    }
    else
    {
      v8 = 0;
      if ( (int)GetAppInfo(Pid, &v8) >= 0 && v8 )
      {
        v2 = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && *((char *)WPP_GLOBAL_Control + 28) < 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_90890ce224d03ac7b34da71504f71581_Traceguids);
      }
      RpcRevertToSelf();
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800063c8  mov     [rsp+arg_0], rbx
0x1800063cd  push    rdi
0x1800063ce  sub     rsp, 20h
0x1800063d2  lea     rdx, [rsp+28h+Pid]; Pid
0x1800063d7  mov     [rsp+28h+Pid], 0
0x1800063df  mov     rdi, rcx
0x1800063e2  xor     bl, bl
0x1800063e4  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800063ea  test    eax, eax
0x1800063ec  jz      short loc_180006442
0x1800063ee  jle     short loc_1800063F8
0x1800063f0  movzx   eax, ax
0x1800063f3  or      eax, 80070000h
0x1800063f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800063ff  lea     rcx, WPP_GLOBAL_Control
0x180006406  cmp     r10, rcx
0x180006409  jz      loc_1800064E4
0x18000640f  test    byte ptr [r10+1Ch], 80h
0x180006414  jz      loc_1800064E4
0x18000641a  cmp     byte ptr [r10+19h], 2
0x18000641f  jb      loc_1800064E4
0x180006425  mov     edx, 12h
0x18000642a  mov     rcx, [r10+10h]
0x18000642e  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x180006435  mov     r9d, eax
0x180006438  call    WPP_SF_d
0x18000643d  jmp     loc_1800064E4
0x180006442  mov     rcx, rdi; BindingHandle
0x180006445  call    cs:__imp_RpcImpersonateClient
0x18000644b  test    eax, eax
0x18000644d  jz      short loc_180006481
0x18000644f  jle     short loc_180006459
0x180006451  movzx   eax, ax
0x180006454  or      eax, 80070000h
0x180006459  mov     r10, cs:WPP_GLOBAL_Control
0x180006460  lea     rcx, WPP_GLOBAL_Control
0x180006467  cmp     r10, rcx
0x18000646a  jz      short loc_1800064E4
0x18000646c  test    byte ptr [r10+1Ch], 80h
0x180006471  jz      short loc_1800064E4
0x180006473  cmp     byte ptr [r10+19h], 2
0x180006478  jb      short loc_1800064E4
0x18000647a  mov     edx, 13h
0x18000647f  jmp     short loc_18000642A
0x180006481  mov     ecx, [rsp+28h+Pid]; dwProcessId
0x180006485  lea     rdx, [rsp+28h+arg_10]; struct _APF_APP_INFO **
0x18000648a  mov     [rsp+28h+arg_10], 0
0x180006493  call    ?GetAppInfo@@YAJKPEAPEAU_APF_APP_INFO@@@Z; GetAppInfo(ulong,_APF_APP_INFO * *)
0x180006498  test    eax, eax
0x18000649a  js      short loc_1800064A8
0x18000649c  cmp     [rsp+28h+arg_10], 0
0x1800064a2  jz      short loc_1800064A8
0x1800064a4  mov     bl, 1
0x1800064a6  jmp     short loc_1800064DE
0x1800064a8  mov     r9, cs:WPP_GLOBAL_Control
0x1800064af  lea     rcx, WPP_GLOBAL_Control
0x1800064b6  cmp     r9, rcx
0x1800064b9  jz      short loc_1800064DE
0x1800064bb  test    byte ptr [r9+1Ch], 80h
0x1800064c0  jz      short loc_1800064DE
0x1800064c2  cmp     byte ptr [r9+19h], 2
0x1800064c7  jb      short loc_1800064DE
0x1800064c9  mov     rcx, [r9+10h]
0x1800064cd  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x1800064d4  mov     edx, 14h
0x1800064d9  call    WPP_SF_
0x1800064de  call    cs:__imp_RpcRevertToSelf
0x1800064e4  mov     al, bl
0x1800064e6  mov     rbx, [rsp+28h+arg_0]
0x1800064eb  add     rsp, 20h
0x1800064ef  pop     rdi
0x1800064f0  retn
```
