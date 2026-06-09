# RAiGetTokenForAxIS

- ea: `0x18003d3d0`
- end: `0x18003d589`
- name: `RAiGetTokenForAxIS`
- size: `441`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, unsigned __int16 *, wchar_t *Source, wchar_t *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180024db0`
- `0x180025724`
- `0x180025bd8`
- `0x18003c4c4`
- `0x18003d3d0`
- `0x18003e53c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d52c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d518`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d518`

## pseudocode

```c
_UNKNOWN **__fastcall RAiGetTokenForAxIS(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        unsigned __int16 *a6,
        wchar_t *Source,
        wchar_t *a8,
        unsigned int a9,
        unsigned __int64 *a10)
{
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rax
  unsigned int v16; // eax
  struct _CONSENTUI_PARAM_HEADER *v17; // rbx
  _UNKNOWN **result; // rax
  unsigned int Reply; // [rsp+70h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+74h] [rbp-34h]
  HLOCAL hMem; // [rsp+78h] [rbp-30h] BYREF

  hMem = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = Source;
    v14 = a8;
    v15 = a6;
    if ( !a8 )
      v14 = L"NULL";
    if ( !Source )
      v13 = L"NULL";
    if ( !a6 )
      v15 = L"NULL";
    WPP_SF_DDDDSSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v14,
      (_DWORD)v13,
      a3,
      a4,
      a5,
      a9,
      (__int64)v15,
      (__int64)v13,
      (__int64)v14);
  }
  v20 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_AxIS_Start);
  v16 = AiBuildAxISParams(Source, a8, (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  v17 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
  Reply = v16;
  if ( !v16 )
  {
    *((_DWORD *)hMem + 13) = v20;
    Reply = AipGetTokenForService(2u, a2, a3, a4, a5, a6, v17, a9, 0, a10, 0, 0, 0, 0);
  }
  LocalFree(v17);
  RpcAsyncCompleteCall(pAsync, &Reply);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (_UNKNOWN **)WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          17,
                          &WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18003d3d0  mov     r11, rsp
0x18003d3d3  mov     [r11+8], rbx
0x18003d3d7  mov     [r11+18h], rbp
0x18003d3db  mov     [r11+10h], rdx
0x18003d3df  push    rdi
0x18003d3e0  push    r12
0x18003d3e2  push    r13
0x18003d3e4  push    r14
0x18003d3e6  push    r15
0x18003d3e8  sub     rsp, 80h
0x18003d3ef  and     qword ptr [r11-30h], 0
0x18003d3f4  mov     ebp, r9d
0x18003d3f7  mov     r14, r8
0x18003d3fa  mov     r13, rcx
0x18003d3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d404  lea     rax, WPP_GLOBAL_Control
0x18003d40b  mov     r15d, [rsp+0A8h+arg_40]
0x18003d413  mov     rbx, [rsp+0A8h+arg_38]
0x18003d41b  mov     rdi, [rsp+0A8h+arg_28]
0x18003d423  mov     r12d, [rsp+0A8h+arg_20]
0x18003d42b  cmp     rcx, rax
0x18003d42e  jz      short loc_18003D485
0x18003d430  test    byte ptr [rcx+1Ch], 1
0x18003d434  jz      short loc_18003D485
0x18003d436  mov     r8, [rsp+0A8h+Source]
0x18003d43e  lea     r9, aNull_0; "NULL"
0x18003d445  mov     rcx, [rcx+10h]
0x18003d449  test    rbx, rbx
0x18003d44c  mov     rdx, rbx
0x18003d44f  mov     rax, rdi
0x18003d452  cmovz   rdx, r9
0x18003d456  cmp     r8, 0
0x18003d45a  mov     [r11-60h], rdx
0x18003d45e  cmovz   r8, r9
0x18003d462  test    rdi, rdi
0x18003d465  mov     [r11-68h], r8
0x18003d469  cmovz   rax, r9
0x18003d46d  mov     r9d, r14d
0x18003d470  mov     [r11-70h], rax
0x18003d474  mov     [r11-78h], r15d
0x18003d478  mov     [r11-80h], r12d
0x18003d47c  mov     [rsp+0A8h+var_88], ebp
0x18003d480  call    WPP_SF_DDDDSSS
0x18003d485  lea     rcx, AppInfo_PerfTrack_Elevation_AxIS_Start; struct _EVENT_DESCRIPTOR *
0x18003d48c  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003d491  mov     rcx, [rsp+0A8h+Source]; Source
0x18003d499  lea     r8, [rsp+0A8h+hMem]; struct _CONSENTUI_PARAM_HEADER **
0x18003d49e  mov     rdx, rbx; wchar_t *
0x18003d4a1  mov     [rsp+0A8h+var_34], eax
0x18003d4a5  call    ?AiBuildAxISParams@@YAKPEBG0PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildAxISParams(ushort const *,ushort const *,_CONSENTUI_PARAM_HEADER * *)
0x18003d4aa  mov     rbx, [rsp+0A8h+hMem]
0x18003d4af  xor     ecx, ecx
0x18003d4b1  mov     [rsp+0A8h+Reply], eax
0x18003d4b5  test    eax, eax
0x18003d4b7  jnz     short loc_18003D515
0x18003d4b9  mov     eax, [rsp+0A8h+var_34]
0x18003d4bd  mov     r9d, ebp; unsigned int
0x18003d4c0  mov     rdx, [rsp+0A8h+arg_8]; void *
0x18003d4c8  mov     r8, r14; unsigned __int64
0x18003d4cb  mov     [rsp+0A8h+var_40], rcx; int *
0x18003d4d0  mov     [rsp+0A8h+var_48], rcx; enum UACPROMPT_POLICY *
0x18003d4d5  mov     [rsp+0A8h+var_50], rcx; char *
0x18003d4da  mov     [rsp+0A8h+var_58], ecx; unsigned int
0x18003d4de  mov     [rbx+34h], eax
0x18003d4e1  mov     rax, [rsp+0A8h+arg_48]
0x18003d4e9  mov     [rsp+0A8h+var_60], rax; unsigned __int64 *
0x18003d4ee  mov     [rsp+0A8h+var_68], rcx; unsigned __int16 *
0x18003d4f3  mov     ecx, 2; unsigned int
0x18003d4f8  mov     [rsp+0A8h+var_70], r15d; unsigned int
0x18003d4fd  mov     [rsp+0A8h+var_78], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003d502  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18003d507  mov     [rsp+0A8h+var_88], r12d; int
0x18003d50c  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003d511  mov     [rsp+0A8h+Reply], eax
0x18003d515  mov     rcx, rbx; hMem
0x18003d518  call    cs:__imp_LocalFree
0x18003d51f  nop     dword ptr [rax+rax+00h]
0x18003d524  lea     rdx, [rsp+0A8h+Reply]; Reply
0x18003d529  mov     rcx, r13; pAsync
0x18003d52c  call    cs:__imp_RpcAsyncCompleteCall
0x18003d533  nop     dword ptr [rax+rax+00h]
0x18003d538  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d53f  lea     rax, WPP_GLOBAL_Control
0x18003d546  cmp     rcx, rax
0x18003d549  jz      short loc_18003D56B
0x18003d54b  test    byte ptr [rcx+1Ch], 1
0x18003d54f  jz      short loc_18003D56B
0x18003d551  mov     r9d, [rsp+0A8h+Reply]
0x18003d556  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003d55d  mov     rcx, [rcx+10h]
0x18003d561  mov     edx, 11h
0x18003d566  call    WPP_SF_D
0x18003d56b  lea     r11, [rsp+0A8h+var_28]
0x18003d573  mov     rbx, [r11+30h]
0x18003d577  mov     rbp, [r11+40h]
0x18003d57b  mov     rsp, r11
0x18003d57e  pop     r15
0x18003d580  pop     r14
0x18003d582  pop     r13
0x18003d584  pop     r12
0x18003d586  pop     rdi
0x18003d587  retn
```
