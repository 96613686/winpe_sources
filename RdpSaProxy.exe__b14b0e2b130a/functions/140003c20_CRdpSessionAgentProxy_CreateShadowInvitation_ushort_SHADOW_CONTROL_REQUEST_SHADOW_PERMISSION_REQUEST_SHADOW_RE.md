# CRdpSessionAgentProxy::CreateShadowInvitation(ushort *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,SHADOW_REQUEST_RESPONSE *,ushort * *)

- ea: `0x140003c20`
- end: `0x140003d7b`
- name: `?CreateShadowInvitation@CRdpSessionAgentProxy@@UEAAJPEAGW4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEAW4SHADOW_REQUEST_RESPONSE@@PEAPEAG@Z`
- size: `347`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *, __int64, unsigned int, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x140002738`
- `0x1400027cc`
- `0x140002818`
- `0x1400035d8`
- `0x140003c20`
- `0x140006010`

## string_xrefs

- `0x140003d44`: `CreateShadowInvitation failed!`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::CreateShadowInvitation(
        CRdpSessionAgentProxy *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  int v10; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edx
  const char *v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // eax

  v10 = CRdpSessionAgentProxy::AccessCheckWellKnownUser(a1, WinNetworkServiceSid);
  if ( v10 >= 0 )
  {
    v14 = *((_QWORD *)a1 + 8);
    if ( v14 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v14 + 24LL))(
              v14,
              a2,
              a3,
              a4,
              a5,
              a6);
      if ( v10 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 21;
        v13 = "CreateShadowInvitation failed!";
        goto LABEL_17;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
          v15,
          -2147483638);
      }
      return (unsigned int)-2147483638;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 19;
    v13 = "User not authorized";
LABEL_17:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v13,
      v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140003c20  push    rbx
0x140003c22  push    rbp
0x140003c23  push    rsi
0x140003c24  push    rdi
0x140003c25  push    r14
0x140003c27  sub     rsp, 40h
0x140003c2b  mov     r14, rdx
0x140003c2e  mov     esi, r9d
0x140003c31  mov     edx, 18h; enum WELL_KNOWN_SID_TYPE
0x140003c36  mov     ebp, r8d
0x140003c39  mov     rdi, rcx
0x140003c3c  call    ?AccessCheckWellKnownUser@CRdpSessionAgentProxy@@AEAAJW4WELL_KNOWN_SID_TYPE@@@Z; CRdpSessionAgentProxy::AccessCheckWellKnownUser(WELL_KNOWN_SID_TYPE)
0x140003c41  mov     ebx, eax
0x140003c43  test    eax, eax
0x140003c45  jns     short loc_140003C88
0x140003c47  mov     rax, cs:WPP_GLOBAL_Control
0x140003c4e  lea     rcx, WPP_GLOBAL_Control
0x140003c55  cmp     rax, rcx
0x140003c58  jz      loc_140003D6E
0x140003c5e  test    byte ptr [rax+1Ch], 8
0x140003c62  jz      loc_140003D6E
0x140003c68  cmp     byte ptr [rax+19h], 2
0x140003c6c  jb      loc_140003D6E
0x140003c72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003c77  mov     edx, 13h
0x140003c7c  lea     rcx, aUserNotAuthori; "User not authorized"
0x140003c83  jmp     loc_140003D4B
0x140003c88  mov     rcx, [rdi+40h]
0x140003c8c  test    rcx, rcx
0x140003c8f  jnz     short loc_140003CE6
0x140003c91  mov     rax, cs:WPP_GLOBAL_Control
0x140003c98  lea     rcx, WPP_GLOBAL_Control
0x140003c9f  cmp     rax, rcx
0x140003ca2  jz      short loc_140003CDC
0x140003ca4  test    byte ptr [rax+1Ch], 8
0x140003ca8  jz      short loc_140003CDC
0x140003caa  cmp     byte ptr [rax+19h], 2
0x140003cae  jb      short loc_140003CDC
0x140003cb0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cbc  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003cc3  mov     edx, 14h
0x140003cc8  mov     dword ptr [rsp+68h+var_48], 8000000Ah
0x140003cd0  mov     r9d, eax
0x140003cd3  mov     rcx, [rcx+10h]
0x140003cd7  call    WPP_SF_Dd
0x140003cdc  mov     ebx, 8000000Ah
0x140003ce1  jmp     loc_140003D6E
0x140003ce6  mov     rdx, [rsp+68h+arg_28]
0x140003cee  mov     r9d, esi
0x140003cf1  mov     rax, [rcx]
0x140003cf4  mov     r8d, ebp
0x140003cf7  mov     [rsp+68h+var_40], rdx
0x140003cfc  mov     rdx, [rsp+68h+arg_20]
0x140003d04  mov     [rsp+68h+var_48], rdx
0x140003d09  mov     rdx, r14
0x140003d0c  mov     rax, [rax+18h]
0x140003d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d15  mov     ebx, eax
0x140003d17  test    eax, eax
0x140003d19  jns     short loc_140003D6E
0x140003d1b  mov     rax, cs:WPP_GLOBAL_Control
0x140003d22  lea     rcx, WPP_GLOBAL_Control
0x140003d29  cmp     rax, rcx
0x140003d2c  jz      short loc_140003D6E
0x140003d2e  test    byte ptr [rax+1Ch], 8
0x140003d32  jz      short loc_140003D6E
0x140003d34  cmp     byte ptr [rax+19h], 2
0x140003d38  jb      short loc_140003D6E
0x140003d3a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140003d3f  mov     edx, 15h
0x140003d44  lea     rcx, aCreateshadowin; "CreateShadowInvitation failed!"
0x140003d4b  mov     dword ptr [rsp+68h+var_40], ebx
0x140003d4f  lea     r8, WPP_a4a5f05f0f7b31c3267dbefd3b846115_Traceguids
0x140003d56  mov     [rsp+68h+var_48], rcx
0x140003d5b  mov     r9d, eax
0x140003d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d65  mov     rcx, [rcx+10h]
0x140003d69  call    WPP_SF_DsD
0x140003d6e  mov     eax, ebx
0x140003d70  add     rsp, 40h
0x140003d74  pop     r14
0x140003d76  pop     rdi
0x140003d77  pop     rsi
0x140003d78  pop     rbp
0x140003d79  pop     rbx
0x140003d7a  retn
```
