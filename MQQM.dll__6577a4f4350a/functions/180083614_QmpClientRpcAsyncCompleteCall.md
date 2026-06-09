# QmpClientRpcAsyncCompleteCall

- ea: `0x180083614`
- end: `0x18008384e`
- name: `QmpClientRpcAsyncCompleteCall`
- size: `570`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180083860`
- `0x180083b60`
- `0x180083c30`
- `0x180083d00`
- `0x180083d90`
- `0x180083e80`
- `0x180084000`
- `0x180084090`
- `0x180084130`
- `0x180084200`
- `0x180084320`
- `0x180084460`
- `0x1800844f0`

## callees

- `0x180009c44`
- `0x18000d1f0`
- `0x18000f35c`
- `0x18002c61c`
- `0x180083614`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180083627`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180083627`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800de881`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800de881`
- `mqsec!ProduceRPCErrorTracing` at `0x180083791`
- `mqsec!ProduceRPCErrorTracing` at `0x180083791`

## pseudocode

```c
__int64 __fastcall QmpClientRpcAsyncCompleteCall(struct _RPC_ASYNC_STATE *a1)
{
  RPC_STATUS v1; // ebx
  int v2; // ecx
  int Reply; // [rsp+38h] [rbp+10h] BYREF

  Reply = 0;
  v1 = RpcAsyncCompleteCall(a1, &Reply);
  if ( v1 )
  {
    if ( v1 == 1745 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 11, &WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids);
      return 3222143115LL;
    }
    else if ( v1 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          13,
          &WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids,
          (unsigned int)v1);
      return LogHR((unsigned __int16)v1 | 0x80070000, (wchar_t *)L"rrcontext", 0x44Fu);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          12,
          &WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids,
          (unsigned int)v1);
      return LogHR(v1, (wchar_t *)L"rrcontext", 0x44Eu);
    }
  }
  else
  {
    v2 = Reply;
    if ( Reply < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        10,
        &WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids,
        (unsigned int)Reply);
      v2 = Reply;
    }
    return LogHR(v2, (wchar_t *)L"rrcontext", 0x44Du);
  }
}

```

## disassembly

```asm
0x180083614  push    rbx
0x180083616  sub     rsp, 20h
0x18008361a  mov     [rsp+28h+Reply], 0
0x180083622  lea     rdx, [rsp+28h+Reply]; Reply
0x180083627  call    cs:__imp_RpcAsyncCompleteCall
0x18008362d  mov     ebx, eax
0x18008362f  test    eax, eax
0x180083631  jnz     short loc_18008368C
0x180083633  mov     ecx, [rsp+28h+Reply]
0x180083637  test    ecx, ecx
0x180083639  jns     short loc_180083675
0x18008363b  lea     rax, WPP_GLOBAL_Control
0x180083642  mov     r10, cs:WPP_GLOBAL_Control
0x180083649  cmp     r10, rax
0x18008364c  jz      short loc_180083675
0x18008364e  test    byte ptr [r10+0BCh], 2
0x180083656  jz      short loc_180083675
0x180083658  lea     edx, [rbx+0Ah]
0x18008365b  mov     r9d, ecx
0x18008365e  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x180083665  mov     rcx, [r10+0B0h]
0x18008366c  call    WPP_SF_d
0x180083671  mov     ecx, [rsp+28h+Reply]; int
0x180083675  mov     r8d, 44Dh; unsigned __int16
0x18008367b  lea     rdx, aRrcontext; "rrcontext"
0x180083682  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180083687  jmp     loc_180083848
0x18008368c  cmp     ebx, 6D1h
0x180083692  jnz     short loc_1800836D2
0x180083694  lea     rax, WPP_GLOBAL_Control
0x18008369b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800836a2  cmp     rcx, rax
0x1800836a5  jz      short loc_1800836C8
0x1800836a7  test    byte ptr [rcx+0BCh], 1
0x1800836ae  jz      short loc_1800836C8
0x1800836b0  mov     edx, 0Bh
0x1800836b5  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x1800836bc  mov     rcx, [rcx+0B0h]
0x1800836c3  call    WPP_SF_
0x1800836c8  mov     eax, 0C00E008Bh
0x1800836cd  jmp     loc_180083848
0x1800836d2  test    ebx, ebx
0x1800836d4  jns     short loc_180083726
0x1800836d6  lea     rax, WPP_GLOBAL_Control
0x1800836dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800836e4  cmp     rcx, rax
0x1800836e7  jz      short loc_18008370D
0x1800836e9  test    byte ptr [rcx+0BCh], 1
0x1800836f0  jz      short loc_18008370D
0x1800836f2  mov     edx, 0Ch
0x1800836f7  mov     r9d, ebx
0x1800836fa  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x180083701  mov     rcx, [rcx+0B0h]
0x180083708  call    WPP_SF_d
0x18008370d  mov     r8d, 44Eh; unsigned __int16
0x180083713  lea     rdx, aRrcontext; "rrcontext"
0x18008371a  mov     ecx, ebx; int
0x18008371c  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x180083721  jmp     loc_180083848
0x180083726  lea     rax, WPP_GLOBAL_Control
0x18008372d  mov     rcx, cs:WPP_GLOBAL_Control
0x180083734  cmp     rcx, rax
0x180083737  jz      short loc_18008375D
0x180083739  test    byte ptr [rcx+0BCh], 1
0x180083740  jz      short loc_18008375D
0x180083742  mov     edx, 0Dh
0x180083747  mov     r9d, ebx
0x18008374a  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x180083751  mov     rcx, [rcx+0B0h]
0x180083758  call    WPP_SF_d
0x18008375d  test    ebx, ebx
0x18008375f  jle     short loc_18008376A
0x180083761  movzx   ebx, bx
0x180083764  or      ebx, 80070000h
0x18008376a  mov     r8d, 44Fh; unsigned __int16
0x180083770  lea     rdx, aRrcontext; "rrcontext"
0x180083777  mov     ecx, ebx; int
0x180083779  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18008377e  jmp     loc_180083848
0x180083783  mov     ebx, eax
0x180083785  mov     edx, 7Fh
0x18008378a  lea     rcx, aRrcontext; "rrcontext"
0x180083791  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x180083797  test    ebx, ebx
0x180083799  jns     short loc_1800837EA
0x18008379b  lea     rax, WPP_GLOBAL_Control
0x1800837a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800837a9  cmp     rcx, rax
0x1800837ac  jz      short loc_1800837D2
0x1800837ae  test    byte ptr [rcx+0BCh], 1
0x1800837b5  jz      short loc_1800837D2
0x1800837b7  mov     edx, 0Eh
0x1800837bc  mov     r9d, ebx
0x1800837bf  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x1800837c6  mov     rcx, [rcx+0B0h]
0x1800837cd  call    WPP_SF_d
0x1800837d2  mov     r8d, 450h; unsigned __int16
0x1800837d8  lea     rdx, aRrcontext; "rrcontext"
0x1800837df  mov     ecx, ebx; int
0x1800837e1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800837e6  mov     eax, ebx
0x1800837e8  jmp     short loc_180083848
0x1800837ea  lea     rax, WPP_GLOBAL_Control
0x1800837f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800837f8  cmp     rcx, rax
0x1800837fb  jz      short loc_180083821
0x1800837fd  test    byte ptr [rcx+0BCh], 1
0x180083804  jz      short loc_180083821
0x180083806  mov     edx, 0Fh
0x18008380b  mov     r9d, ebx
0x18008380e  lea     r8, WPP_08c720015ae03e1075d08cdaabe4771e_Traceguids
0x180083815  mov     rcx, [rcx+0B0h]
0x18008381c  call    WPP_SF_d
0x180083821  test    ebx, ebx
0x180083823  jle     short loc_180083830
0x180083825  movzx   ebx, bx
0x180083828  or      ebx, 80070000h
0x18008382e  test    ebx, ebx
0x180083830  jns     short loc_180083846
0x180083832  mov     r8d, 451h; unsigned __int16
0x180083838  lea     rdx, aRrcontext; "rrcontext"
0x18008383f  mov     ecx, ebx; int
0x180083841  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180083846  mov     eax, ebx
0x180083848  add     rsp, 20h
0x18008384c  pop     rbx
0x18008384d  retn
0x1800de873  push    rbp
0x1800de875  sub     rsp, 20h
0x1800de879  mov     rbp, rdx
0x1800de87c  mov     rcx, [rcx]
0x1800de87f  mov     ecx, [rcx]; ExceptionCode
0x1800de881  call    cs:__imp_I_RpcExceptionFilter
0x1800de887  nop
0x1800de888  add     rsp, 20h
0x1800de88c  pop     rbp
0x1800de88d  retn
```
