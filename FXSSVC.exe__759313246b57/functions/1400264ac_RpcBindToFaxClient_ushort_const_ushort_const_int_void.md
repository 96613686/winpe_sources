# RpcBindToFaxClient(ushort const *,ushort const *,int,void * *)

- ea: `0x1400264ac`
- end: `0x1400267db`
- name: `?RpcBindToFaxClient@@YAKPEBG0HPEAPEAX@Z`
- size: `815`
- prototype: `__int64 __fastcall(wchar_t *String2, RPC_WSTR Endpoint, unsigned int AuthzSvc, RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011fa0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400264ac`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002660f`
- `KERNEL32!GetLastError` at `0x14002660f`
- `KERNEL32!GetComputerNameW` at `0x14002653d`
- `KERNEL32!GetComputerNameW` at `0x14002653d`
- `msvcrt!_wcsicmp` at `0x140026558`
- `msvcrt!_wcsicmp` at `0x14002657d`
- `msvcrt!_wcsicmp` at `0x140026558`
- `msvcrt!_wcsicmp` at `0x14002657d`
- `RPCRT4!RpcBindingFree` at `0x14002670a`
- `RPCRT4!RpcBindingFree` at `0x14002670a`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400265c5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400265c5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14002665b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14002665b`
- `RPCRT4!RpcStringFreeW` at `0x14002666d`
- `RPCRT4!RpcStringFreeW` at `0x14002666d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400266c7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400266c7`
- `RPCRT4!RpcBindingSetOption` at `0x140026730`
- `RPCRT4!RpcBindingSetOption` at `0x140026730`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcBindToFaxClient(
        wchar_t *String2,
        RPC_WSTR Endpoint,
        unsigned int AuthzSvc,
        RPC_BINDING_HANDLE *Binding)
{
  unsigned __int16 *v8; // rdx
  unsigned int v9; // eax
  __int64 result; // rax
  DWORD LastError; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  RPC_BINDING_HANDLE v14; // rcx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  DWORD nSize; // [rsp+40h] [rbp-19h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-11h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-9h] BYREF
  WCHAR Buffer[16]; // [rsp+60h] [rbp+7h] BYREF

  String = 0;
  nSize = 16;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  *Binding = 0;
  if ( AuthzSvc )
  {
    String2 = 0;
  }
  else
  {
    if ( !String2 )
      goto LABEL_13;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
      }
      return v12;
    }
    if ( !_wcsicmp(Buffer, String2) || *String2 == 92 && String2[1] == 92 && !_wcsicmp(Buffer, String2 + 2) )
LABEL_13:
      String2 = L"127.0.0.1";
  }
  v8 = L"ncalrpc";
  if ( !AuthzSvc )
    v8 = L"ncacn_ip_tcp";
  v9 = RpcStringBindingComposeW(0, v8, String2, Endpoint, (RPC_WSTR)&Class, &String);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v9);
    }
    return 3221225495LL;
  }
  v13 = RpcBindingFromStringBindingW(String, Binding);
  RpcStringFreeW(&String);
  if ( !v13 )
  {
    v14 = *Binding;
    if ( *Binding )
    {
      if ( AuthzSvc
        || (*(_QWORD *)&SecurityQOS.Version = 1,
            SecurityQOS.IdentityTracking = 0,
            SecurityQOS.ImpersonationType = 2,
            (v12 = RpcBindingSetAuthInfoExW(v14, 0, 6u, 0xAu, 0, 0, &SecurityQOS)) == 0) )
      {
        v12 = RpcBindingSetOption(*Binding, 0xCu, 0x7530u);
        if ( !v12 )
          return 0;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v16 = 86;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v16 = 85;
      }
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v12);
LABEL_36:
      RpcBindingFree(Binding);
      *Binding = 0;
      return v12;
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
  }
  *Binding = 0;
  result = 1210;
  if ( v13 != 1706 && v13 != 1707 )
    return 3221225495LL;
  return result;
}

```

## disassembly

```asm
0x1400264ac  mov     [rsp-8+arg_10], rbx
0x1400264b1  push    rbp
0x1400264b2  push    rsi
0x1400264b3  push    rdi
0x1400264b4  push    r13
0x1400264b6  push    r14
0x1400264b8  lea     rbp, [rsp-37h]
0x1400264bd  sub     rsp, 90h
0x1400264c4  mov     rax, cs:__security_cookie
0x1400264cb  xor     rax, rsp
0x1400264ce  mov     [rbp+57h+var_30], rax
0x1400264d2  mov     rdi, r9
0x1400264d5  mov     [rbp+57h+String], 0
0x1400264dd  mov     esi, r8d
0x1400264e0  mov     [rbp+57h+nSize], 10h
0x1400264e7  mov     r14, rdx
0x1400264ea  mov     rbx, rcx
0x1400264ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400264f4  lea     r13, WPP_GLOBAL_Control
0x1400264fb  cmp     rcx, r13
0x1400264fe  jz      short loc_140026521
0x140026500  test    byte ptr [rcx+1Ch], 4
0x140026504  jz      short loc_140026521
0x140026506  cmp     byte ptr [rcx+19h], 5
0x14002650a  jb      short loc_140026521
0x14002650c  mov     rcx, [rcx+10h]
0x140026510  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140026517  mov     edx, 51h ; 'Q'
0x14002651c  call    WPP_SF_
0x140026521  mov     qword ptr [rdi], 0
0x140026528  test    esi, esi
0x14002652a  jz      short loc_140026530
0x14002652c  xor     ebx, ebx
0x14002652e  jmp     short loc_140026594
0x140026530  test    rbx, rbx
0x140026533  jz      short loc_14002658D
0x140026535  lea     rdx, [rbp+57h+nSize]; nSize
0x140026539  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x14002653d  call    cs:__imp_GetComputerNameW
0x140026544  nop     dword ptr [rax+rax+00h]
0x140026549  test    eax, eax
0x14002654b  jz      loc_14002660F
0x140026551  mov     rdx, rbx; String2
0x140026554  lea     rcx, [rbp+57h+Buffer]; String1
0x140026558  call    cs:__imp__wcsicmp
0x14002655f  nop     dword ptr [rax+rax+00h]
0x140026564  test    eax, eax
0x140026566  jz      short loc_14002658D
0x140026568  cmp     word ptr [rbx], 5Ch ; '\'
0x14002656c  jnz     short loc_140026594
0x14002656e  cmp     word ptr [rbx+2], 5Ch ; '\'
0x140026573  jnz     short loc_140026594
0x140026575  lea     rdx, [rbx+4]; String2
0x140026579  lea     rcx, [rbp+57h+Buffer]; String1
0x14002657d  call    cs:__imp__wcsicmp
0x140026584  nop     dword ptr [rax+rax+00h]
0x140026589  test    eax, eax
0x14002658b  jnz     short loc_140026594
0x14002658d  lea     rbx, a127001; "127.0.0.1"
0x140026594  lea     rax, ProtSeq; "ncacn_ip_tcp"
0x14002659b  test    esi, esi
0x14002659d  lea     rdx, aNcalrpc; "ncalrpc"
0x1400265a4  mov     r9, r14; Endpoint
0x1400265a7  cmovz   rdx, rax; ProtSeq
0x1400265ab  mov     r8, rbx; NetworkAddr
0x1400265ae  lea     rax, [rbp+57h+String]
0x1400265b2  xor     ecx, ecx; ObjUuid
0x1400265b4  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x1400265b9  lea     rax, Class
0x1400265c0  mov     [rsp+0B0h+Options], rax; Options
0x1400265c5  call    cs:__imp_RpcStringBindingComposeW
0x1400265cc  nop     dword ptr [rax+rax+00h]
0x1400265d1  test    eax, eax
0x1400265d3  jz      short loc_140026654
0x1400265d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265dc  cmp     rcx, r13
0x1400265df  jz      short loc_140026605
0x1400265e1  test    byte ptr [rcx+1Ch], 4
0x1400265e5  jz      short loc_140026605
0x1400265e7  cmp     byte ptr [rcx+19h], 2
0x1400265eb  jb      short loc_140026605
0x1400265ed  mov     rcx, [rcx+10h]
0x1400265f1  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400265f8  mov     edx, 53h ; 'S'
0x1400265fd  mov     r9d, eax
0x140026600  call    WPP_SF_d
0x140026605  mov     eax, 0C0000017h
0x14002660a  jmp     loc_1400267B7
0x14002660f  call    cs:__imp_GetLastError
0x140026616  nop     dword ptr [rax+rax+00h]
0x14002661b  mov     ebx, eax
0x14002661d  mov     rcx, cs:WPP_GLOBAL_Control
0x140026624  cmp     rcx, r13
0x140026627  jz      short loc_14002664D
0x140026629  test    byte ptr [rcx+1Ch], 4
0x14002662d  jz      short loc_14002664D
0x14002662f  cmp     byte ptr [rcx+19h], 2
0x140026633  jb      short loc_14002664D
0x140026635  mov     rcx, [rcx+10h]
0x140026639  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140026640  mov     edx, 52h ; 'R'
0x140026645  mov     r9d, eax
0x140026648  call    WPP_SF_d
0x14002664d  mov     eax, ebx
0x14002664f  jmp     loc_1400267B7
0x140026654  mov     rcx, [rbp+57h+String]; StringBinding
0x140026658  mov     rdx, rdi; Binding
0x14002665b  call    cs:__imp_RpcBindingFromStringBindingW
0x140026662  nop     dword ptr [rax+rax+00h]
0x140026667  lea     rcx, [rbp+57h+String]; String
0x14002666b  mov     ebx, eax
0x14002666d  call    cs:__imp_RpcStringFreeW
0x140026674  nop     dword ptr [rax+rax+00h]
0x140026679  test    ebx, ebx
0x14002667b  jnz     loc_140026765
0x140026681  mov     rcx, [rdi]; Binding
0x140026684  test    rcx, rcx
0x140026687  jz      loc_140026765
0x14002668d  test    esi, esi
0x14002668f  jnz     loc_140026722
0x140026695  lea     rax, [rbp+57h+var_60]
0x140026699  mov     qword ptr [rbp+57h+var_60.Version], 1
0x1400266a1  mov     [rsp+0B0h+SecurityQOS], rax; SecurityQOS
0x1400266a6  lea     r9d, [rbx+0Ah]; AuthnSvc
0x1400266aa  mov     dword ptr [rsp+0B0h+StringBinding], esi; AuthzSvc
0x1400266ae  lea     r8d, [rbx+6]; AuthnLevel
0x1400266b2  xor     edx, edx; ServerPrincName
0x1400266b4  mov     [rsp+0B0h+Options], 0; AuthIdentity
0x1400266bd  mov     [rbp+57h+var_60.IdentityTracking], esi
0x1400266c0  mov     [rbp+57h+var_60.ImpersonationType], 2
0x1400266c7  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1400266ce  nop     dword ptr [rax+rax+00h]
0x1400266d3  mov     ebx, eax
0x1400266d5  test    eax, eax
0x1400266d7  jz      short loc_140026722
0x1400266d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266e0  cmp     rcx, r13
0x1400266e3  jz      short loc_140026707
0x1400266e5  test    byte ptr [rcx+1Ch], 4
0x1400266e9  jz      short loc_140026707
0x1400266eb  cmp     byte ptr [rcx+19h], 2
0x1400266ef  jb      short loc_140026707
0x1400266f1  lea     edx, [rsi+55h]
0x1400266f4  mov     rcx, [rcx+10h]
0x1400266f8  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400266ff  mov     r9d, ebx
0x140026702  call    WPP_SF_d
0x140026707  mov     rcx, rdi; Binding
0x14002670a  call    cs:__imp_RpcBindingFree
0x140026711  nop     dword ptr [rax+rax+00h]
0x140026716  mov     qword ptr [rdi], 0
0x14002671d  jmp     loc_14002664D
0x140026722  mov     rcx, [rdi]; hBinding
0x140026725  mov     edx, 0Ch; option
0x14002672a  mov     r8d, 7530h; optionValue
0x140026730  call    cs:__imp_RpcBindingSetOption
0x140026737  nop     dword ptr [rax+rax+00h]
0x14002673c  mov     ebx, eax
0x14002673e  test    eax, eax
0x140026740  jz      short loc_140026761
0x140026742  mov     rcx, cs:WPP_GLOBAL_Control
0x140026749  cmp     rcx, r13
0x14002674c  jz      short loc_140026707
0x14002674e  test    byte ptr [rcx+1Ch], 4
0x140026752  jz      short loc_140026707
0x140026754  cmp     byte ptr [rcx+19h], 2
0x140026758  jb      short loc_140026707
0x14002675a  mov     edx, 56h ; 'V'
0x14002675f  jmp     short loc_1400266F4
0x140026761  xor     eax, eax
0x140026763  jmp     short loc_1400267B7
0x140026765  mov     rcx, cs:WPP_GLOBAL_Control
0x14002676c  cmp     rcx, r13
0x14002676f  jz      short loc_140026795
0x140026771  test    byte ptr [rcx+1Ch], 4
0x140026775  jz      short loc_140026795
0x140026777  cmp     byte ptr [rcx+19h], 2
0x14002677b  jb      short loc_140026795
0x14002677d  mov     rcx, [rcx+10h]
0x140026781  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140026788  mov     edx, 54h ; 'T'
0x14002678d  mov     r9d, ebx
0x140026790  call    WPP_SF_d
0x140026795  mov     qword ptr [rdi], 0
0x14002679c  mov     eax, 4BAh
0x1400267a1  cmp     ebx, 6AAh
0x1400267a7  jz      short loc_1400267B7
0x1400267a9  cmp     ebx, 6ABh
0x1400267af  mov     ecx, 0C0000017h
0x1400267b4  cmovnz  eax, ecx
0x1400267b7  mov     rcx, [rbp+57h+var_30]
0x1400267bb  xor     rcx, rsp; StackCookie
0x1400267be  call    __security_check_cookie
0x1400267c3  mov     rbx, [rsp+0B0h+arg_10]
0x1400267cb  add     rsp, 90h
0x1400267d2  pop     r14
0x1400267d4  pop     r13
0x1400267d6  pop     rdi
0x1400267d7  pop     rsi
0x1400267d8  pop     rbp
0x1400267d9  retn
```
