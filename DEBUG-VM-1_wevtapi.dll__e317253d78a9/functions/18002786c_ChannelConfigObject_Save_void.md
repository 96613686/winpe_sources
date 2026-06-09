# ChannelConfigObject::Save(void)

- ea: `0x18002786c`
- end: `0x180027a1f`
- name: `?Save@ChannelConfigObject@@QEAAXXZ`
- size: `435`
- prototype: `void __fastcall(ChannelConfigObject *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180026360`

## callees

- `0x180006aec`
- `0x18000decc`
- `0x180023548`
- `0x1800249f0`
- `0x18002786c`
- `0x180027b4c`
- `0x180038fb4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800278fd`
- `RPCRT4!NdrClientCall3` at `0x1800278fd`

## pseudocode

```c
void __fastcall ChannelConfigObject::Save(ChannelConfigObject *this)
{
  int v2; // edx
  int v3; // ecx
  _BYTE *v4; // r9
  char v5; // al
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int128 pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+50h] [rbp-30h]
  unsigned int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  int v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h] BYREF
  int v16; // [rsp+70h] [rbp-10h]

  v15 = 0;
  v16 = 0;
  LastErrInfo::Reset(this);
  v4 = (_BYTE *)*((_QWORD *)this + 5);
  if ( (v4[4] & 1) != 0 && (byte_18004B801 & 4) != 0 )
  {
    v5 = v4[8];
    LOBYTE(v4) = v4[56];
    McTemplateU0zut_EventWriteTransfer(v3, v2, *((_QWORD *)this + 7), (_DWORD)v4, v5);
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x15u,
                            0,
                            *(_QWORD *)(*((_QWORD *)this + 6) + 72LL),
                            *((_QWORD *)this + 7),
                            *((_DWORD *)this + 28),
                            (char *)this + 32,
                            &v15).Pointer;
  v8 = Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, Pointer);
    }
    v11 = 0;
    v12 = v8;
    v13 = -1;
    pExceptionObject = 0;
    v14 = 157;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (_DWORD)v15 )
  {
    LastErrInfo::Set((LastErrInfo *)v7.Pointer, (struct tag_RpcInfo *)&v15);
    v9 = v15;
    if ( !(_DWORD)v15 )
      v9 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids, v9);
    }
    v11 = 0;
    v12 = v9;
    v13 = -1;
    pExceptionObject = 0;
    v14 = 163;
    throw (EvtException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002786c  mov     [rsp-8+arg_8], rbx
0x180027871  push    rbp
0x180027872  mov     rbp, rsp
0x180027875  sub     rsp, 80h
0x18002787c  mov     rax, cs:__security_cookie
0x180027883  xor     rax, rsp
0x180027886  mov     [rbp+var_8], rax
0x18002788a  xor     eax, eax
0x18002788c  mov     rbx, rcx
0x18002788f  mov     [rbp+var_18], rax
0x180027893  mov     [rbp+var_10], eax
0x180027896  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18002789b  mov     r9, [rbx+28h]
0x18002789f  test    byte ptr [r9+4], 1
0x1800278a4  jz      short loc_1800278C5
0x1800278a6  test    cs:byte_18004B801, 4
0x1800278ad  jz      short loc_1800278C5
0x1800278af  movzx   eax, byte ptr [r9+8]
0x1800278b4  mov     r9b, [r9+38h]
0x1800278b8  mov     r8, [rbx+38h]
0x1800278bc  mov     dword ptr [rsp+80h+var_60], eax
0x1800278c0  call    McTemplateU0zut_EventWriteTransfer
0x1800278c5  mov     r9, [rbx+30h]
0x1800278c9  lea     rax, [rbx+20h]
0x1800278cd  lea     rcx, [rbp+var_18]
0x1800278d1  xor     r8d, r8d; pReturnValue
0x1800278d4  mov     [rsp+80h+var_48], rcx
0x1800278d9  lea     rcx, pProxyInfo; pProxyInfo
0x1800278e0  mov     [rsp+80h+var_50], rax
0x1800278e5  mov     eax, [rbx+70h]
0x1800278e8  mov     r9, [r9+48h]
0x1800278ec  lea     edx, [r8+15h]; nProcNum
0x1800278f0  mov     [rsp+80h+var_58], eax
0x1800278f4  mov     rax, [rbx+38h]
0x1800278f8  mov     [rsp+80h+var_60], rax
0x1800278fd  call    cs:__imp_NdrClientCall3
0x180027903  mov     rbx, rax
0x180027906  test    eax, eax
0x180027908  jz      short loc_180027976
0x18002790a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027911  lea     rdx, WPP_GLOBAL_Control
0x180027918  cmp     rcx, rdx
0x18002791b  jz      short loc_180027944
0x18002791d  test    dword ptr [rcx+1Ch], 40000h
0x180027924  jz      short loc_180027944
0x180027926  cmp     byte ptr [rcx+19h], 2
0x18002792a  jb      short loc_180027944
0x18002792c  mov     rcx, [rcx+10h]
0x180027930  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x180027937  mov     edx, 0Dh
0x18002793c  mov     r9d, ebx
0x18002793f  call    WPP_SF_D
0x180027944  xorps   xmm0, xmm0
0x180027947  mov     [rbp+var_30], 0
0x18002794f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027956  mov     [rbp+var_28], ebx
0x180027959  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002795d  mov     [rbp+var_24], 0FFFFFFFFh
0x180027964  movdqu  [rbp+pExceptionObject], xmm0
0x180027969  mov     [rbp+var_20], 9Dh
0x180027970  call    _CxxThrowException_0
0x180027976  cmp     dword ptr [rbp+var_18], 0
0x18002797a  jz      loc_180027A02
0x180027980  lea     rdx, [rbp+var_18]; struct tag_RpcInfo *
0x180027984  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x180027989  mov     ebx, dword ptr [rbp+var_18]
0x18002798c  mov     eax, 507h
0x180027991  test    ebx, ebx
0x180027993  cmovz   ebx, eax
0x180027996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002799d  lea     rdx, WPP_GLOBAL_Control
0x1800279a4  cmp     rcx, rdx
0x1800279a7  jz      short loc_1800279D0
0x1800279a9  test    dword ptr [rcx+1Ch], 40000h
0x1800279b0  jz      short loc_1800279D0
0x1800279b2  cmp     byte ptr [rcx+19h], 2
0x1800279b6  jb      short loc_1800279D0
0x1800279b8  mov     rcx, [rcx+10h]
0x1800279bc  lea     r8, WPP_970b3d70c99a3bbc832a1e51198c3047_Traceguids
0x1800279c3  mov     edx, 0Eh
0x1800279c8  mov     r9d, ebx
0x1800279cb  call    WPP_SF_D
0x1800279d0  xorps   xmm0, xmm0
0x1800279d3  mov     [rbp+var_30], 0
0x1800279db  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800279e2  mov     [rbp+var_28], ebx
0x1800279e5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800279e9  mov     [rbp+var_24], 0FFFFFFFFh
0x1800279f0  movdqu  [rbp+pExceptionObject], xmm0
0x1800279f5  mov     [rbp+var_20], 0A3h
0x1800279fc  call    _CxxThrowException_0
0x180027a02  mov     rcx, [rbp+var_8]
0x180027a06  xor     rcx, rsp; StackCookie
0x180027a09  call    __security_check_cookie
0x180027a0e  mov     rbx, [rsp+80h+arg_8]
0x180027a16  add     rsp, 80h
0x180027a1d  pop     rbp
0x180027a1e  retn
```
