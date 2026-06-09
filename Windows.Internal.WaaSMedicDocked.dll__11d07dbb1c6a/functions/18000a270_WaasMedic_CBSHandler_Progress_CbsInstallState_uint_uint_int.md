# WaasMedic::CBSHandler::Progress(_CbsInstallState,uint,uint,int *)

- ea: `0x18000a270`
- end: `0x18000a346`
- name: `?Progress@CBSHandler@WaasMedic@@UEAAJW4_CbsInstallState@@IIPEAH@Z`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800048e4`
- `0x18000a270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a2e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a2e9`

## pseudocode

```c
__int64 __fastcall WaasMedic::CBSHandler::Progress(_DWORD *a1, int a2, __int64 a3, __int64 a4, _DWORD *pcbData)
{
  _DWORD *v5; // rdi
  char v6; // bl
  int ValueW; // eax
  bool v8; // zf
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pvData; // [rsp+58h] [rbp+10h] BYREF

  v5 = pcbData;
  v6 = 1;
  *pcbData = 1;
  if ( a2 )
  {
    if ( a2 == 4 )
    {
      a1[11] = 1;
    }
    else if ( a2 == 7 )
    {
      a1[9] = 1;
    }
  }
  else
  {
    a1[10] = 1;
  }
  pvData = 0;
  LODWORD(pcbData) = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\WaaS\\WaaSMedic\\State",
             L"Cancel",
             0x10u,
             0,
             &pvData,
             (LPDWORD)&pcbData);
  v8 = ValueW == 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v8 = ValueW == 0;
  }
  if ( v8 )
  {
    if ( pvData != 1 )
      return 0;
  }
  else
  {
    if ( ValueW == -2147024894 )
      return 0;
    if ( ValueW < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\cbshandler.cpp",
        (const char *)(unsigned int)ValueW,
        pdwType);
      return 0;
    }
    v6 = 0;
  }
  if ( v6 )
    *v5 = 3;
  return 0;
}

```

## disassembly

```asm
0x18000a270  mov     [rsp+arg_0], rbx
0x18000a275  push    rdi
0x18000a276  sub     rsp, 40h
0x18000a27a  mov     rdi, [rsp+48h+arg_20]
0x18000a27f  mov     ebx, 1
0x18000a284  mov     [rdi], ebx
0x18000a286  test    edx, edx
0x18000a288  jz      short loc_18000A29E
0x18000a28a  cmp     edx, 4
0x18000a28d  jz      short loc_18000A299
0x18000a28f  cmp     edx, 7
0x18000a292  jnz     short loc_18000A2A1
0x18000a294  mov     [rcx+24h], ebx
0x18000a297  jmp     short loc_18000A2A1
0x18000a299  mov     [rcx+2Ch], ebx
0x18000a29c  jmp     short loc_18000A2A1
0x18000a29e  mov     [rcx+28h], ebx
0x18000a2a1  lea     rax, [rsp+48h+arg_20]
0x18000a2a6  mov     [rsp+48h+arg_8], 0
0x18000a2ae  mov     [rsp+48h+pcbData], rax; pcbData
0x18000a2b3  lea     r8, aCancel; "Cancel"
0x18000a2ba  lea     rax, [rsp+48h+arg_8]
0x18000a2bf  mov     dword ptr [rsp+48h+arg_20], 4
0x18000a2c7  mov     [rsp+48h+pvData], rax; pvData
0x18000a2cc  lea     rdx, aSystemWaasWaas; "SYSTEM\\WaaS\\WaaSMedic\\State"
0x18000a2d3  mov     r9d, 10h; dwFlags
0x18000a2d9  mov     [rsp+48h+pdwType], 0; int
0x18000a2e2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a2e9  call    cs:__imp_RegGetValueW
0x18000a2ef  test    eax, eax
0x18000a2f1  jle     short loc_18000A2FD
0x18000a2f3  movzx   eax, ax
0x18000a2f6  or      eax, 80070000h
0x18000a2fb  test    eax, eax
0x18000a2fd  jz      short loc_18000A329
0x18000a2ff  cmp     eax, 80070002h
0x18000a304  jz      short loc_18000A339
0x18000a306  test    eax, eax
0x18000a308  jns     short loc_18000A325
0x18000a30a  mov     rcx, [rsp+48h]; this
0x18000a30f  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000a316  mov     r9d, eax; char *
0x18000a319  mov     edx, 0EAh; void *
0x18000a31e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a323  jmp     short loc_18000A339
0x18000a325  xor     bl, bl
0x18000a327  jmp     short loc_18000A32F
0x18000a329  cmp     [rsp+48h+arg_8], ebx
0x18000a32d  jnz     short loc_18000A339
0x18000a32f  test    bl, bl
0x18000a331  jz      short loc_18000A339
0x18000a333  mov     dword ptr [rdi], 3
0x18000a339  mov     rbx, [rsp+48h+arg_0]
0x18000a33e  xor     eax, eax
0x18000a340  add     rsp, 40h
0x18000a344  pop     rdi
0x18000a345  retn
```
