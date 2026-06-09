# FWGetGlobalConfig2

- ea: `0x18000ef00`
- end: `0x18000f096`
- name: `FWGetGlobalConfig2`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180005e0c`
- `0x18000ef00`
- `0x18000f0a0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000ef4e`
- `ntdll!EtwEventWrite` at `0x18000efea`
- `ntdll!EtwEventWrite` at `0x18000ef4e`
- `ntdll!EtwEventWrite` at `0x18000efea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ef77`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ef77`

## pseudocode

```c
__int64 __fastcall FWGetGlobalConfig2(
        unsigned __int16 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        int *a7,
        _DWORD *a8)
{
  unsigned int v12; // eax
  unsigned int v13; // ebx
  FwPolicy2 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int64 v18; // rax

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetGlobalConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  if ( a3 == 6 )
    goto LABEL_8;
  if ( !a2 )
    goto LABEL_8;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(a2 + 2 * v18) );
  if ( v18 <= 0xFF )
  {
LABEL_8:
    v12 = Int_FWGetOrSetGlobalConfig(1, a1, a2, a3, 0, a4, a5, a6, a7, a8);
    v13 = v12;
    if ( v12 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 79;
        v17 = v12;
LABEL_15:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
      }
    }
  }
  else
  {
    v13 = 87;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 78;
      v17 = 87;
      goto LABEL_15;
    }
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetGlobalConfig, 0, 0);
  return v13;
}

```

## disassembly

```asm
0x18000ef00  push    rbx
0x18000ef02  push    rbp
0x18000ef03  push    rsi
0x18000ef04  push    rdi
0x18000ef05  push    r12
0x18000ef07  push    r13
0x18000ef09  push    r14
0x18000ef0b  push    r15
0x18000ef0d  sub     rsp, 58h
0x18000ef11  mov     r14, [rsp+98h+arg_28]
0x18000ef19  movzx   esi, cx
0x18000ef1c  mov     rcx, cs:g_Provider
0x18000ef23  mov     ebp, r9d
0x18000ef26  mov     r15, [rsp+98h+arg_30]
0x18000ef2e  mov     ebx, r8d
0x18000ef31  mov     r12, [rsp+98h+arg_38]
0x18000ef39  mov     rdi, rdx
0x18000ef3c  test    rcx, rcx
0x18000ef3f  jz      short loc_18000EF5A
0x18000ef41  xor     r9d, r9d
0x18000ef44  lea     rdx, MPS_CLNT_API_Enter_GetGlobalConfig
0x18000ef4b  xor     r8d, r8d
0x18000ef4e  call    cs:__imp_EtwEventWrite
0x18000ef55  nop     dword ptr [rax+rax+00h]
0x18000ef5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef61  lea     r13, WPP_GLOBAL_Control
0x18000ef68  cmp     rcx, r13
0x18000ef6b  jz      short loc_18000EF77
0x18000ef6d  test    byte ptr [rcx+1Ch], 8
0x18000ef71  jnz     loc_18000F036
0x18000ef77  call    cs:__imp_GetTickCount64
0x18000ef7e  nop     dword ptr [rax+rax+00h]
0x18000ef83  cmp     ebx, 6
0x18000ef86  jz      short loc_18000EF91
0x18000ef88  test    rdi, rdi
0x18000ef8b  jnz     loc_18000F050
0x18000ef91  mov     eax, [rsp+98h+arg_20]
0x18000ef98  mov     r9d, ebx
0x18000ef9b  mov     [rsp+98h+var_50], r12
0x18000efa0  mov     r8, rdi
0x18000efa3  mov     [rsp+98h+var_58], r15
0x18000efa8  movzx   edx, si
0x18000efab  mov     [rsp+98h+var_60], r14
0x18000efb0  mov     ecx, 1
0x18000efb5  mov     [rsp+98h+var_68], eax
0x18000efb9  mov     [rsp+98h+var_70], ebp
0x18000efbd  mov     [rsp+98h+var_78], 0
0x18000efc6  call    Int_FWGetOrSetGlobalConfig
0x18000efcb  mov     ebx, eax
0x18000efcd  test    eax, eax
0x18000efcf  jnz     short loc_18000F00A
0x18000efd1  mov     rcx, cs:g_Provider
0x18000efd8  test    rcx, rcx
0x18000efdb  jz      short loc_18000EFF6
0x18000efdd  xor     r9d, r9d
0x18000efe0  lea     rdx, MPS_CLNT_API_Exit_GetGlobalConfig
0x18000efe7  xor     r8d, r8d
0x18000efea  call    cs:__imp_EtwEventWrite
0x18000eff1  nop     dword ptr [rax+rax+00h]
0x18000eff6  mov     eax, ebx
0x18000eff8  add     rsp, 58h
0x18000effc  pop     r15
0x18000effe  pop     r14
0x18000f000  pop     r13
0x18000f002  pop     r12
0x18000f004  pop     rdi
0x18000f005  pop     rsi
0x18000f006  pop     rbp
0x18000f007  pop     rbx
0x18000f008  retn
0x18000f00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f011  cmp     rcx, r13
0x18000f014  jz      short loc_18000EFD1
0x18000f016  test    byte ptr [rcx+1Ch], 1
0x18000f01a  jz      short loc_18000EFD1
0x18000f01c  mov     edx, 4Fh ; 'O'
0x18000f021  mov     r9d, eax
0x18000f024  mov     rcx, [rcx+10h]
0x18000f028  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f02f  call    WPP_SF_d
0x18000f034  jmp     short loc_18000EFD1
0x18000f036  mov     rcx, [rcx+10h]
0x18000f03a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f041  mov     edx, 4Dh ; 'M'
0x18000f046  call    WPP_SF_
0x18000f04b  jmp     loc_18000EF77
0x18000f050  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f057  inc     rax
0x18000f05a  cmp     word ptr [rdi+rax*2], 0
0x18000f05f  jnz     short loc_18000F057
0x18000f061  cmp     rax, 0FFh
0x18000f067  jbe     loc_18000EF91
0x18000f06d  mov     ebx, 57h ; 'W'
0x18000f072  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f079  cmp     rcx, r13
0x18000f07c  jz      loc_18000EFD1
0x18000f082  test    byte ptr [rcx+1Ch], 1
0x18000f086  jz      loc_18000EFD1
0x18000f08c  mov     edx, 4Eh ; 'N'
0x18000f091  mov     r9d, ebx
0x18000f094  jmp     short loc_18000F024
```
