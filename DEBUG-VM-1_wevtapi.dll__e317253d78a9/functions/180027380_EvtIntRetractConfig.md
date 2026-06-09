# EvtIntRetractConfig

- ea: `0x180027380`
- end: `0x1800274fc`
- name: `EvtIntRetractConfig`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180007940`
- `0x180007aa0`
- `0x180023548`
- `0x180027380`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800274dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800274dd`
- `RPCRT4!NdrClientCall3` at `0x180027443`
- `RPCRT4!NdrClientCall3` at `0x180027443`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EvtIntRetractConfig(__int64 a1, __int64 a2, int a3)
{
  unsigned int Pointer; // ebx
  unsigned int v6; // edi
  DWORD v7; // ebx
  int v9; // [rsp+28h] [rbp-70h]
  EvtException *v10; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-60h] BYREF
  unsigned int v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+54h] [rbp-44h]
  char v14; // [rsp+5Ch] [rbp-3Ch]
  __int128 pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  __int64 v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]
  int v19; // [rsp+80h] [rbp-18h]
  __int64 v20; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    if ( (a3 & 0xFFFFFFFE) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v16 = 0;
      v17 = 87;
      v18 = -1;
      v19 = 417;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v20);
    v9 = a3;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x10u,
                              0,
                              *(_QWORD *)(v20 + 72),
                              a2,
                              v9).Pointer;
    v6 = 0;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, Pointer);
      }
      v11[0] = &word_18004024A;
      v11[1] = 0;
      v11[2] = 0;
      v12 = Pointer;
      v13 = -1;
      v14 = 0;
      throw (EvtException *)v11;
    }
    v7 = 0;
    wmi::AutoRef<Object>::Release(&v20);
  }
  catch ( EvtException *v10 )
  {
    v6 = 0;
    v7 = *((_DWORD *)v10 + 6);
  }
  SetLastError(v7);
  LOBYTE(v6) = v7 == 0;
  return v6;
}

```

## disassembly

```asm
0x180027380  mov     [rsp+arg_0], rbx
0x180027385  push    rdi
0x180027386  sub     rsp, 90h
0x18002738d  mov     ebx, r8d
0x180027390  mov     rdi, rdx
0x180027393  test    ebx, 0FFFFFFFEh
0x180027399  jz      short loc_18002740F
0x18002739b  lea     rax, WPP_GLOBAL_Control
0x1800273a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273a9  cmp     rcx, rax
0x1800273ac  jz      short loc_1800273D3
0x1800273ae  test    byte ptr [rcx+1Ch], 1
0x1800273b2  jz      short loc_1800273D3
0x1800273b4  cmp     byte ptr [rcx+19h], 2
0x1800273b8  jb      short loc_1800273D3
0x1800273ba  mov     edx, 11h
0x1800273bf  lea     r9d, [rdx+46h]
0x1800273c3  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x1800273ca  mov     rcx, [rcx+10h]
0x1800273ce  call    WPP_SF_D
0x1800273d3  xorps   xmm0, xmm0
0x1800273d6  movdqu  [rsp+98h+pExceptionObject], xmm0
0x1800273dc  xor     edi, edi
0x1800273de  mov     [rsp+98h+var_28], rdi
0x1800273e3  mov     [rsp+98h+var_20], 57h ; 'W'
0x1800273eb  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x1800273f3  mov     [rsp+98h+var_18], 1A1h
0x1800273fe  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027405  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002740a  call    _CxxThrowException_0
0x18002740f  mov     rdx, rcx
0x180027412  lea     rcx, [rsp+98h+arg_18]; void *
0x18002741a  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18002741f  nop
0x180027420  mov     [rsp+98h+var_70], ebx
0x180027424  mov     [rsp+98h+var_78], rdi
0x180027429  mov     r9, [rsp+98h+arg_18]
0x180027431  mov     r9, [r9+48h]
0x180027435  xor     r8d, r8d; pReturnValue
0x180027438  lea     edx, [r8+10h]; nProcNum
0x18002743c  lea     rcx, pProxyInfo; pProxyInfo
0x180027443  call    cs:__imp_NdrClientCall3
0x180027449  mov     rbx, rax
0x18002744c  xor     edi, edi
0x18002744e  test    ebx, ebx
0x180027450  jz      short loc_1800274C0
0x180027452  lea     rax, WPP_GLOBAL_Control
0x180027459  mov     rcx, cs:WPP_GLOBAL_Control
0x180027460  cmp     rcx, rax
0x180027463  jz      short loc_180027487
0x180027465  test    byte ptr [rcx+1Ch], 1
0x180027469  jz      short loc_180027487
0x18002746b  cmp     byte ptr [rcx+19h], 2
0x18002746f  jb      short loc_180027487
0x180027471  lea     edx, [rdi+12h]
0x180027474  mov     r9d, ebx
0x180027477  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18002747e  mov     rcx, [rcx+10h]
0x180027482  call    WPP_SF_D
0x180027487  lea     rax, word_18004024A
0x18002748e  mov     [rsp+98h+var_60], rax
0x180027493  mov     [rsp+98h+var_58], rdi
0x180027498  mov     [rsp+98h+var_50], rdi
0x18002749d  mov     [rsp+98h+var_48], ebx
0x1800274a1  mov     [rsp+98h+var_44], 0FFFFFFFFFFFFFFFFh
0x1800274aa  mov     [rsp+98h+var_3C], dil
0x1800274af  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800274b6  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x1800274bb  call    _CxxThrowException_0
0x1800274c0  mov     ebx, edi
0x1800274c2  lea     rcx, [rsp+98h+arg_18]; void *
0x1800274ca  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x1800274cf  nop
0x1800274d0  jmp     short loc_1800274DB
0x1800274d2  xor     edi, edi
0x1800274d4  mov     ebx, [rsp+98h+arg_10]
0x1800274db  mov     ecx, ebx; dwErrCode
0x1800274dd  call    cs:__imp_SetLastError
0x1800274e3  test    ebx, ebx
0x1800274e5  setz    dil
0x1800274e9  mov     eax, edi
0x1800274eb  mov     rbx, [rsp+98h+arg_0]
0x1800274f3  add     rsp, 90h
0x1800274fa  pop     rdi
0x1800274fb  retn
```
