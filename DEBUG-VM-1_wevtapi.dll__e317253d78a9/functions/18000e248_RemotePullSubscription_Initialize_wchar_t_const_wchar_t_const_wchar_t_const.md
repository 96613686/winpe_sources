# RemotePullSubscription::Initialize(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18000e248`
- end: `0x18000e563`
- name: `?Initialize@RemotePullSubscription@@QEAAXPEB_W00@Z`
- size: `795`
- prototype: `void __fastcall(RemotePullSubscription *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000d050`

## callees

- `0x180006aec`
- `0x18000a020`
- `0x18000a298`
- `0x18000de84`
- `0x18000decc`
- `0x18000df24`
- `0x18000dff8`
- `0x18000e248`
- `0x18000e73c`
- `0x18000e890`
- `0x180023548`
- `0x1800249f0`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e3bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e3bb`
- `RPCRT4!NdrClientCall3` at `0x18000e2f6`
- `RPCRT4!NdrClientCall3` at `0x18000e2f6`

## pseudocode

```c
void __fastcall RemotePullSubscription::Initialize(
        RemotePullSubscription *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  unsigned int *v10; // r13
  unsigned int Pointer; // ebx
  BookmarkChannels *v12; // rax
  unsigned int i; // ebx
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rdi
  DWORD CurrentProcessId; // eax
  int v18; // [rsp+70h] [rbp-69h]
  __int128 pExceptionObject; // [rsp+78h] [rbp-61h] BYREF
  __int64 v20; // [rsp+88h] [rbp-51h]
  int v21; // [rsp+90h] [rbp-49h]
  int v22; // [rsp+94h] [rbp-45h]
  int v23; // [rsp+98h] [rbp-41h]
  char v24; // [rsp+9Ch] [rbp-3Dh]
  _QWORD v25[2]; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD v26[2]; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD v27[2]; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-9h] BYREF
  int v29; // [rsp+D8h] [rbp-1h]

  v28 = 0;
  v29 = 0;
  LastErrInfo::Reset(this);
  v8 = tlx::replace<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 48);
  v9 = tlx::replace<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 40);
  v10 = (unsigned int *)((char *)this + 268);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0,
                            0,
                            *(_QWORD *)(*((_QWORD *)this + 4) + 72LL),
                            a2,
                            a3,
                            a4,
                            *((_DWORD *)this + 66),
                            v9,
                            v8,
                            (char *)this + 268,
                            (char *)this + 208,
                            &v28).Pointer;
  v18 = 0;
  if ( !v28 && v29 )
  {
    v18 = v29;
    v29 = 0;
  }
  LastErrInfo::Set(0, (struct tag_RpcInfo *)&v28);
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, Pointer);
    }
    v21 = Pointer;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v24 = 0;
    v23 = -1;
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    v20 = 0;
    v22 = -1;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, 1359);
    }
    v20 = 0;
    v21 = 1359;
    v22 = -1;
    pExceptionObject = 0;
    v23 = 258;
    throw (EvtException *)&pExceptionObject;
  }
  v12 = (BookmarkChannels *)operator new(0x28u);
  v25[0] = v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 4) = 0;
    v12 = BookmarkChannels::BookmarkChannels(v12);
  }
  wmi::AutoRef<BookmarkChannels>::operator=((char *)this + 216, v12);
  for ( i = 0; i < *v10; ++i )
    BookmarkChannels::AddChannel(
      *((BookmarkChannels **)this + 27),
      *(const wchar_t **)(*((_QWORD *)this + 26) + 16LL * i));
  Session::AddControllableObject(*((Session **)this + 4), *((void **)this + 6));
  if ( !a4 )
    a4 = (const wchar_t *)&unk_180040824;
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( a4[v15] );
  v16 = -1;
  if ( !a3 )
    a3 = (const wchar_t *)&unk_180040824;
  do
    ++v16;
  while ( a3[v16] );
  if ( !a2 )
    a2 = (const wchar_t *)&unk_180040824;
  do
    ++v14;
  while ( a2[v14] );
  CurrentProcessId = GetCurrentProcessId();
  v25[0] = a4;
  v25[1] = v15;
  v26[0] = a3;
  v26[1] = v16;
  v27[0] = a2;
  v27[1] = v14;
  LogSubscriptionRpcTrackingEvent(CurrentProcessId, v18, (unsigned int)v27, (unsigned int)v26, (__int64)v25, 0);
}

```

## disassembly

```asm
0x18000e248  push    rbp
0x18000e24a  push    rbx
0x18000e24b  push    rsi
0x18000e24c  push    rdi
0x18000e24d  push    r12
0x18000e24f  push    r13
0x18000e251  push    r14
0x18000e253  push    r15
0x18000e255  lea     rbp, [rsp-1Fh]
0x18000e25a  sub     rsp, 0F8h
0x18000e261  mov     rax, cs:__security_cookie
0x18000e268  xor     rax, rsp
0x18000e26b  mov     [rbp+57h+var_50], rax
0x18000e26f  xor     eax, eax
0x18000e271  mov     r12, r9
0x18000e274  mov     [rbp+57h+var_60], rax
0x18000e278  mov     r15, r8
0x18000e27b  mov     [rbp+57h+var_58], eax
0x18000e27e  mov     r14, rdx
0x18000e281  mov     rsi, rcx
0x18000e284  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18000e289  lea     rcx, [rsi+30h]
0x18000e28d  call    ??$replace@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>> &)
0x18000e292  lea     rcx, [rsi+28h]
0x18000e296  mov     rbx, rax
0x18000e299  call    ??$replace@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>> &)
0x18000e29e  mov     r9, [rsi+20h]
0x18000e2a2  lea     rdx, [rbp+57h+var_60]
0x18000e2a6  mov     [rsp+130h+var_D0], rdx
0x18000e2ab  lea     rcx, [rsi+0D0h]
0x18000e2b2  mov     [rsp+130h+var_D8], rcx
0x18000e2b7  lea     r13, [rsi+10Ch]
0x18000e2be  mov     [rsp+130h+var_E0], r13
0x18000e2c3  lea     rcx, pProxyInfo; pProxyInfo
0x18000e2ca  mov     r9, [r9+48h]
0x18000e2ce  xor     r8d, r8d; pReturnValue
0x18000e2d1  mov     [rsp+130h+var_E8], rbx
0x18000e2d6  xor     edx, edx; nProcNum
0x18000e2d8  mov     [rsp+130h+var_F0], rax
0x18000e2dd  mov     eax, [rsi+108h]
0x18000e2e3  mov     [rsp+130h+var_F8], eax
0x18000e2e7  mov     [rsp+130h+var_100], r12
0x18000e2ec  mov     [rsp+130h+var_108], r15
0x18000e2f1  mov     [rsp+130h+var_110], r14
0x18000e2f6  call    cs:__imp_NdrClientCall3
0x18000e2fc  xor     ecx, ecx; this
0x18000e2fe  mov     rbx, rax
0x18000e301  mov     [rbp+57h+var_C0], ecx
0x18000e304  cmp     dword ptr [rbp+57h+var_60], ecx
0x18000e307  jz      loc_18000E4AB
0x18000e30d  lea     rdx, [rbp+57h+var_60]; struct tag_RpcInfo *
0x18000e311  call    ?Set@LastErrInfo@@QEAAXAEAUtag_RpcInfo@@@Z; LastErrInfo::Set(tag_RpcInfo &)
0x18000e316  xor     edx, edx
0x18000e318  test    ebx, ebx
0x18000e31a  jnz     loc_18000E45C
0x18000e320  cmp     [rsi+28h], rdx
0x18000e324  jz      loc_18000E4F5
0x18000e32a  cmp     [rsi+30h], rdx
0x18000e32e  jz      loc_18000E4F5
0x18000e334  lea     ecx, [rdx+28h]; dwBytes
0x18000e337  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e33c  mov     [rbp+57h+var_90], rax
0x18000e340  test    rax, rax
0x18000e343  jnz     loc_18000E419
0x18000e349  lea     rdi, [rsi+0D8h]
0x18000e350  mov     rdx, rax
0x18000e353  mov     rcx, rdi
0x18000e356  call    ??4?$AutoRef@VBookmarkChannels@@@wmi@@QEAAAEAV01@PEAVBookmarkChannels@@@Z; wmi::AutoRef<BookmarkChannels>::operator=(BookmarkChannels *)
0x18000e35b  xor     ebx, ebx
0x18000e35d  cmp     [r13+0], ebx
0x18000e361  ja      loc_18000E436
0x18000e367  mov     rdx, [rsi+30h]; void *
0x18000e36b  mov     rcx, [rsi+20h]; this
0x18000e36f  call    ?AddControllableObject@Session@@QEAAXPEAX@Z; Session::AddControllableObject(void *)
0x18000e374  xor     r13d, r13d
0x18000e377  lea     rax, unk_180040824
0x18000e37e  test    r12, r12
0x18000e381  cmovz   r12, rax
0x18000e385  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e389  mov     rsi, rbx
0x18000e38c  inc     rsi
0x18000e38f  cmp     [r12+rsi*2], r13w
0x18000e394  jnz     short loc_18000E38C
0x18000e396  test    r15, r15
0x18000e399  mov     rdi, rbx
0x18000e39c  cmovz   r15, rax
0x18000e3a0  inc     rdi
0x18000e3a3  cmp     [r15+rdi*2], r13w
0x18000e3a8  jnz     short loc_18000E3A0
0x18000e3aa  test    r14, r14
0x18000e3ad  cmovz   r14, rax
0x18000e3b1  inc     rbx
0x18000e3b4  cmp     [r14+rbx*2], r13w
0x18000e3b9  jnz     short loc_18000E3B1
0x18000e3bb  call    cs:__imp_GetCurrentProcessId
0x18000e3c1  mov     edx, [rbp+57h+var_C0]
0x18000e3c4  lea     rcx, [rbp+57h+var_90]
0x18000e3c8  mov     byte ptr [rsp+130h+var_108], r13b
0x18000e3cd  lea     r9, [rbp+57h+var_80]
0x18000e3d1  mov     [rsp+130h+var_110], rcx
0x18000e3d6  lea     r8, [rbp+57h+var_70]
0x18000e3da  mov     ecx, eax
0x18000e3dc  mov     [rbp+57h+var_90], r12
0x18000e3e0  mov     [rbp+57h+var_88], rsi
0x18000e3e4  mov     [rbp+57h+var_80], r15
0x18000e3e8  mov     [rbp+57h+var_78], rdi
0x18000e3ec  mov     [rbp+57h+var_70], r14
0x18000e3f0  mov     [rbp+57h+var_68], rbx
0x18000e3f4  call    ?LogSubscriptionRpcTrackingEvent@@YAXKKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@00_N@Z; LogSubscriptionRpcTrackingEvent(ulong,ulong,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x18000e3f9  mov     rcx, [rbp+57h+var_50]
0x18000e3fd  xor     rcx, rsp; StackCookie
0x18000e400  call    __security_check_cookie
0x18000e405  add     rsp, 0F8h
0x18000e40c  pop     r15
0x18000e40e  pop     r14
0x18000e410  pop     r13
0x18000e412  pop     r12
0x18000e414  pop     rdi
0x18000e415  pop     rsi
0x18000e416  pop     rbx
0x18000e417  pop     rbp
0x18000e418  retn
0x18000e419  xor     ecx, ecx
0x18000e41b  xorps   xmm0, xmm0
0x18000e41e  movups  xmmword ptr [rax], xmm0
0x18000e421  movups  xmmword ptr [rax+10h], xmm0
0x18000e425  mov     [rax+20h], rcx
0x18000e429  mov     rcx, rax; this
0x18000e42c  call    ??0BookmarkChannels@@QEAA@XZ; BookmarkChannels::BookmarkChannels(void)
0x18000e431  jmp     loc_18000E349
0x18000e436  mov     rdx, [rsi+0D0h]
0x18000e43d  mov     rcx, [rdi]; this
0x18000e440  mov     eax, ebx
0x18000e442  add     rax, rax
0x18000e445  mov     rdx, [rdx+rax*8]; wchar_t *
0x18000e449  call    ?AddChannel@BookmarkChannels@@QEAAXPEB_W@Z; BookmarkChannels::AddChannel(wchar_t const *)
0x18000e44e  inc     ebx
0x18000e450  cmp     ebx, [r13+0]
0x18000e454  jnb     loc_18000E367
0x18000e45a  jmp     short loc_18000E436
0x18000e45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e463  lea     rax, WPP_GLOBAL_Control
0x18000e46a  cmp     rcx, rax
0x18000e46d  jnz     short loc_18000E4CA
0x18000e46f  mov     [rbp+57h+var_A0], ebx
0x18000e472  lea     rax, word_18004024A
0x18000e479  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e47d  mov     qword ptr [rbp+57h+pExceptionObject+8], rdx
0x18000e481  mov     [rbp+57h+var_94], dl
0x18000e484  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000e488  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000e48f  mov     [rbp+57h+var_98], ebx
0x18000e492  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x18000e496  mov     [rbp+57h+var_A8], 0
0x18000e49e  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000e4a5  call    _CxxThrowException_0
0x18000e4ab  cmp     dword ptr [rbp+57h+var_60+4], ecx
0x18000e4ae  jnz     loc_18000E30D
0x18000e4b4  mov     eax, [rbp+57h+var_58]
0x18000e4b7  test    eax, eax
0x18000e4b9  jz      loc_18000E30D
0x18000e4bf  mov     [rbp+57h+var_C0], eax
0x18000e4c2  mov     [rbp+57h+var_58], ecx
0x18000e4c5  jmp     loc_18000E30D
0x18000e4ca  test    byte ptr [rcx+1Ch], 80h
0x18000e4ce  jz      short loc_18000E46F
0x18000e4d0  cmp     byte ptr [rcx+19h], 2
0x18000e4d4  jb      short loc_18000E46F
0x18000e4d6  mov     rcx, [rcx+10h]
0x18000e4da  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x18000e4e1  mov     edx, 12h
0x18000e4e6  mov     r9d, ebx
0x18000e4e9  call    WPP_SF_D
0x18000e4ee  xor     edx, edx
0x18000e4f0  jmp     loc_18000E46F
0x18000e4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4fc  lea     rax, WPP_GLOBAL_Control
0x18000e503  mov     ebx, 54Fh
0x18000e508  cmp     rcx, rax
0x18000e50b  jz      short loc_18000E531
0x18000e50d  test    byte ptr [rcx+1Ch], 80h
0x18000e511  jz      short loc_18000E531
0x18000e513  cmp     byte ptr [rcx+19h], 2
0x18000e517  jb      short loc_18000E531
0x18000e519  mov     rcx, [rcx+10h]
0x18000e51d  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x18000e524  mov     edx, 13h
0x18000e529  mov     r9d, ebx
0x18000e52c  call    WPP_SF_D
0x18000e531  xorps   xmm0, xmm0
0x18000e534  mov     [rbp+57h+var_A8], 0
0x18000e53c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000e543  mov     [rbp+57h+var_A0], ebx
0x18000e546  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000e54a  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x18000e551  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18000e556  mov     [rbp+57h+var_98], 102h
0x18000e55d  call    _CxxThrowException_0
```
