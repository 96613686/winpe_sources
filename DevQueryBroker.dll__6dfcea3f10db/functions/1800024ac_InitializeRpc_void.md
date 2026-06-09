# InitializeRpc(void)

- ea: `0x1800024ac`
- end: `0x1800027a0`
- name: `?InitializeRpc@@YAJXZ`
- size: `756`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ec0`

## callees

- `0x1800024ac`
- `0x1800027a8`
- `0x18000a19e`
- `0x18000a1d0`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800026dc`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800026dc`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180002723`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180002723`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000257b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800025e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000257b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800025e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002780`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002780`

## string_xrefs

- `0x180002667`: `DevQueryBroker client query RPC interface`

## pseudocode

```c
__int64 InitializeRpc(void)
{
  signed int v0; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  signed int LastError; // eax
  int v5; // eax
  int v6; // eax
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+68h] [rbp-98h]
  __int128 v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v15; // [rsp+98h] [rbp-68h] BYREF
  __int128 v16; // [rsp+A0h] [rbp-60h]
  int v17; // [rsp+B0h] [rbp-50h]
  __int64 v18; // [rsp+B4h] [rbp-4Ch]
  __int64 v19; // [rsp+C0h] [rbp-40h]
  __int128 *v20; // [rsp+C8h] [rbp-38h]
  const wchar_t *v21; // [rsp+D0h] [rbp-30h]
  PSECURITY_DESCRIPTOR v22; // [rsp+D8h] [rbp-28h]
  WCHAR StringSecurityDescriptor[28]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v24[26]; // [rsp+118h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  wcscpy(StringSecurityDescriptor, L"D:(A;;GR;;;AU)(A;;GR;;AC)");
  hMem = 0;
  v14 = 0;
  wcscpy(v24, L"D:(A;;GR;;;WD)(A;;GR;;AC)");
  v10 = 0;
  memset_0(&v15, 0, 0x48u);
  v11 = 0;
  g_bDqbRpcIdle = 0;
  g_dqbRpcState = 0;
  v12 = 0;
  v13 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v24, 1u, &hMem, 0) )
    {
      LODWORD(v10) = 1;
      *((_QWORD *)&v10 + 1) = DQB_ClientQuery_RpcEndpointObject;
      v14 = 0;
      v15 = qword_18000CFD0;
      v17 = 41;
      v20 = &v10;
      v16 = 0;
      v21 = L"DevQueryBroker client query RPC interface";
      v22 = SecurityDescriptor;
      *(_QWORD *)&v12 = L"ncalrpc";
      *(_QWORD *)&v13 = hMem;
      v18 = 1234;
      v19 = 0;
      v11 = 0;
      *((_QWORD *)&v12 + 1) = 0;
      DWORD2(v13) = 10;
      v5 = RpcServerInterfaceGroupCreateW(
             &v14,
             1,
             &v11,
             1,
             30,
             DqbRpcInterfaceGroupIdleCallback,
             0,
             &g_dqbRpcInterfaceGroup);
      v1 = v5;
      if ( v5 )
      {
        if ( v5 >= 0 )
          v1 = (unsigned __int16)v5 | 0x80010000;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v3 = 12;
          goto LABEL_7;
        }
      }
      else
      {
        g_dqbRpcState |= 1u;
        v6 = RpcServerInterfaceGroupActivate(g_dqbRpcInterfaceGroup);
        v1 = v6;
        if ( v6 )
        {
          if ( v6 >= 0 )
            v1 = (unsigned __int16)v6 | 0x80010000;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v3 = 13;
            goto LABEL_7;
          }
        }
        else
        {
          g_dqbRpcState |= 2u;
          v1 = 0;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 11;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v0 = GetLastError();
    v1 = v0;
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 10;
LABEL_7:
      WPP_SF_D(v2[2], v3, WPP_015184568a1939f18fdf8e711bb07b4f_Traceguids, v1);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x1800024ac  push    rbp
0x1800024ae  push    rbx
0x1800024af  push    rsi
0x1800024b0  push    rdi
0x1800024b1  lea     rbp, [rsp-68h]
0x1800024b6  sub     rsp, 168h
0x1800024bd  mov     rax, cs:__security_cookie
0x1800024c4  xor     rax, rsp
0x1800024c7  mov     [rbp+80h+var_30], rax
0x1800024cb  movups  xmm0, xmmword ptr cs:aDAGrAuAGrAc; "D:(A;;GR;;;AU)(A;;GR;;;AC)"
0x1800024d2  xor     edi, edi
0x1800024d4  xor     edx, edx; Val
0x1800024d6  movups  xmm1, xmmword ptr cs:aDAGrAuAGrAc+10h; ";;;AU)(A;;GR;;;AC)"
0x1800024dd  lea     rcx, [rbp+80h+var_E8]; void *
0x1800024e1  mov     [rsp+180h+SecurityDescriptor], rdi
0x1800024e6  movups  xmmword ptr [rbp+80h+StringSecurityDescriptor], xmm0
0x1800024ea  lea     r8d, [rdi+48h]; Size
0x1800024ee  mov     [rsp+180h+hMem], rdi
0x1800024f3  movups  xmm0, xmmword ptr cs:aDAGrAuAGrAc+20h; ";;GR;;;AC)"
0x1800024fa  mov     [rbp+80h+var_F0], edi
0x1800024fd  movups  [rbp+80h+var_90], xmm1
0x180002501  movsd   xmm1, qword ptr cs:aDAGrAuAGrAc+2Eh; "AC)"
0x180002509  movups  [rbp+80h+var_80], xmm0
0x18000250d  movups  xmm0, xmmword ptr cs:aDAGrWdAGrAc; "D:(A;;GR;;;WD)(A;;GR;;;AC)"
0x180002514  movsd   qword ptr [rbp+80h+var_80+0Eh], xmm1
0x180002519  movups  xmm1, xmmword ptr cs:aDAGrWdAGrAc+10h; ";;;WD)(A;;GR;;;AC)"
0x180002520  movups  xmmword ptr [rbp+80h+var_68], xmm0
0x180002524  movups  xmm0, xmmword ptr cs:aDAGrWdAGrAc+20h; ";;GR;;;AC)"
0x18000252b  movups  xmmword ptr [rbp+80h+var_68+10h], xmm1
0x18000252f  movsd   xmm1, qword ptr cs:aDAGrWdAGrAc+2Eh; "AC)"
0x180002537  movups  [rbp+80h+var_48], xmm0
0x18000253b  xorps   xmm0, xmm0
0x18000253e  movsd   qword ptr [rbp+80h+var_48+0Eh], xmm1
0x180002543  movups  [rsp+180h+var_130], xmm0
0x180002548  call    memset_0
0x18000254d  xorps   xmm0, xmm0
0x180002550  mov     [rsp+180h+var_120], edi
0x180002554  lea     esi, [rdi+1]
0x180002557  mov     cs:?g_bDqbRpcIdle@@3HA, edi; int g_bDqbRpcIdle
0x18000255d  mov     edx, esi; StringSDRevision
0x18000255f  mov     cs:?g_dqbRpcState@@3KA, edi; ulong g_dqbRpcState
0x180002565  xor     r9d, r9d; SecurityDescriptorSize
0x180002568  lea     r8, [rsp+180h+SecurityDescriptor]; SecurityDescriptor
0x18000256d  lea     rcx, [rbp+80h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180002571  movups  [rsp+180h+var_118], xmm0
0x180002576  movups  [rsp+180h+var_108], xmm0
0x18000257b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002581  test    eax, eax
0x180002583  jnz     short loc_1800025D8
0x180002585  call    cs:__imp_GetLastError
0x18000258b  mov     ebx, eax
0x18000258d  test    eax, eax
0x18000258f  jle     short loc_18000259A
0x180002591  movzx   ebx, ax
0x180002594  or      ebx, 80070000h
0x18000259a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025a1  lea     rax, WPP_GLOBAL_Control
0x1800025a8  cmp     rcx, rax
0x1800025ab  jz      loc_180002766
0x1800025b1  cmp     byte ptr [rcx+19h], 2
0x1800025b5  jb      loc_180002766
0x1800025bb  mov     edx, 0Ah
0x1800025c0  mov     rcx, [rcx+10h]
0x1800025c4  lea     r8, WPP_015184568a1939f18fdf8e711bb07b4f_Traceguids
0x1800025cb  mov     r9d, ebx
0x1800025ce  call    WPP_SF_D
0x1800025d3  jmp     loc_180002766
0x1800025d8  xor     r9d, r9d; SecurityDescriptorSize
0x1800025db  lea     r8, [rsp+180h+hMem]; SecurityDescriptor
0x1800025e0  mov     edx, esi; StringSDRevision
0x1800025e2  lea     rcx, [rbp+80h+var_68]; StringSecurityDescriptor
0x1800025e6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800025ec  test    eax, eax
0x1800025ee  jnz     short loc_18000262D
0x1800025f0  call    cs:__imp_GetLastError
0x1800025f6  mov     ebx, eax
0x1800025f8  test    eax, eax
0x1800025fa  jle     short loc_180002605
0x1800025fc  movzx   ebx, ax
0x1800025ff  or      ebx, 80070000h
0x180002605  mov     rcx, cs:WPP_GLOBAL_Control
0x18000260c  lea     rax, WPP_GLOBAL_Control
0x180002613  cmp     rcx, rax
0x180002616  jz      loc_180002766
0x18000261c  cmp     byte ptr [rcx+19h], 2
0x180002620  jb      loc_180002766
0x180002626  mov     edx, 0Bh
0x18000262b  jmp     short loc_1800025C0
0x18000262d  lea     rax, DQB_ClientQuery_RpcEndpointObject
0x180002634  mov     dword ptr [rsp+180h+var_130], esi
0x180002638  mov     qword ptr [rsp+180h+var_130+8], rax
0x18000263d  lea     r8, [rsp+180h+var_120]
0x180002642  lea     rax, qword_18000CFD0
0x180002649  mov     [rbp+80h+var_F0], edi
0x18000264c  mov     [rbp+80h+var_E8], rax
0x180002650  lea     rcx, [rbp+80h+var_F0]
0x180002654  lea     rax, [rsp+180h+var_130]
0x180002659  mov     [rbp+80h+var_D0], 29h ; ')'
0x180002660  mov     [rbp+80h+var_B8], rax
0x180002664  xorps   xmm0, xmm0
0x180002667  lea     rax, aDevquerybroker_1; "DevQueryBroker client query RPC interfa"...
0x18000266e  movdqa  [rbp+80h+var_E0], xmm0
0x180002673  mov     [rbp+80h+var_B0], rax
0x180002677  mov     r9d, esi
0x18000267a  mov     rax, [rsp+180h+SecurityDescriptor]
0x18000267f  mov     edx, esi
0x180002681  mov     [rbp+80h+var_A8], rax
0x180002685  lea     rax, aNcalrpc; "ncalrpc"
0x18000268c  mov     qword ptr [rsp+180h+var_118], rax
0x180002691  mov     rax, [rsp+180h+hMem]
0x180002696  mov     qword ptr [rsp+180h+var_108], rax
0x18000269b  lea     rax, ?g_dqbRpcInterfaceGroup@@3PEAXEA; void * g_dqbRpcInterfaceGroup
0x1800026a2  mov     [rsp+180h+var_148], rax
0x1800026a7  lea     rax, ?DqbRpcInterfaceGroupIdleCallback@@YAXPEAX0K@Z; DqbRpcInterfaceGroupIdleCallback(void *,void *,ulong)
0x1800026ae  mov     [rsp+180h+var_150], rdi
0x1800026b3  mov     [rsp+180h+var_158], rax
0x1800026b8  mov     [rsp+180h+var_160], 1Eh
0x1800026c0  mov     [rbp+80h+var_CC], 4D2h
0x1800026c8  mov     [rbp+80h+var_C0], rdi
0x1800026cc  mov     [rsp+180h+var_120], edi
0x1800026d0  mov     qword ptr [rsp+180h+var_118+8], rdi
0x1800026d5  mov     dword ptr [rbp+80h+var_108+8], 0Ah
0x1800026dc  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x1800026e2  mov     ebx, eax
0x1800026e4  test    eax, eax
0x1800026e6  jz      short loc_180002716
0x1800026e8  js      short loc_1800026F3
0x1800026ea  movzx   ebx, ax
0x1800026ed  or      ebx, 80010000h
0x1800026f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026fa  lea     rax, WPP_GLOBAL_Control
0x180002701  cmp     rcx, rax
0x180002704  jz      short loc_180002766
0x180002706  cmp     byte ptr [rcx+19h], 2
0x18000270a  jb      short loc_180002766
0x18000270c  mov     edx, 0Ch
0x180002711  jmp     loc_1800025C0
0x180002716  mov     rcx, cs:?g_dqbRpcInterfaceGroup@@3PEAXEA; void * g_dqbRpcInterfaceGroup
0x18000271d  or      cs:?g_dqbRpcState@@3KA, esi; ulong g_dqbRpcState
0x180002723  call    cs:__imp_RpcServerInterfaceGroupActivate
0x180002729  mov     ebx, eax
0x18000272b  test    eax, eax
0x18000272d  jz      short loc_18000275D
0x18000272f  js      short loc_18000273A
0x180002731  movzx   ebx, ax
0x180002734  or      ebx, 80010000h
0x18000273a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002741  lea     rax, WPP_GLOBAL_Control
0x180002748  cmp     rcx, rax
0x18000274b  jz      short loc_180002766
0x18000274d  cmp     byte ptr [rcx+19h], 2
0x180002751  jb      short loc_180002766
0x180002753  mov     edx, 0Dh
0x180002758  jmp     loc_1800025C0
0x18000275d  or      cs:?g_dqbRpcState@@3KA, 2; ulong g_dqbRpcState
0x180002764  mov     ebx, edi
0x180002766  mov     rcx, [rsp+180h+hMem]; hMem
0x18000276b  test    rcx, rcx
0x18000276e  jz      short loc_180002776
0x180002770  call    cs:__imp_LocalFree
0x180002776  mov     rcx, [rsp+180h+SecurityDescriptor]; hMem
0x18000277b  test    rcx, rcx
0x18000277e  jz      short loc_180002786
0x180002780  call    cs:__imp_LocalFree
0x180002786  mov     eax, ebx
0x180002788  mov     rcx, [rbp+80h+var_30]
0x18000278c  xor     rcx, rsp; StackCookie
0x18000278f  call    __security_check_cookie
0x180002794  add     rsp, 168h
0x18000279b  pop     rdi
0x18000279c  pop     rsi
0x18000279d  pop     rbx
0x18000279e  pop     rbp
0x18000279f  retn
```
