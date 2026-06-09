# RAiGetTokenForAxIS

- ea: `0x18003efa0`
- end: `0x18003f159`
- name: `RAiGetTokenForAxIS`
- size: `441`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, unsigned __int16 *, wchar_t *Source, wchar_t *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800234a0`
- `0x180023e14`
- `0x1800242c8`
- `0x18003e094`
- `0x18003efa0`
- `0x18004010c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f0fc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f0fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f0e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f0e8`

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
0x18003efa0  mov     r11, rsp
0x18003efa3  mov     [r11+8], rbx
0x18003efa7  mov     [r11+18h], rbp
0x18003efab  mov     [r11+10h], rdx
0x18003efaf  push    rdi
0x18003efb0  push    r12
0x18003efb2  push    r13
0x18003efb4  push    r14
0x18003efb6  push    r15
0x18003efb8  sub     rsp, 80h
0x18003efbf  and     qword ptr [r11-30h], 0
0x18003efc4  mov     ebp, r9d
0x18003efc7  mov     r14, r8
0x18003efca  mov     r13, rcx
0x18003efcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efd4  lea     rax, WPP_GLOBAL_Control
0x18003efdb  mov     r15d, [rsp+0A8h+arg_40]
0x18003efe3  mov     rbx, [rsp+0A8h+arg_38]
0x18003efeb  mov     rdi, [rsp+0A8h+arg_28]
0x18003eff3  mov     r12d, [rsp+0A8h+arg_20]
0x18003effb  cmp     rcx, rax
0x18003effe  jz      short loc_18003F055
0x18003f000  test    byte ptr [rcx+1Ch], 1
0x18003f004  jz      short loc_18003F055
0x18003f006  mov     r8, [rsp+0A8h+Source]
0x18003f00e  lea     r9, aNull_0; "NULL"
0x18003f015  mov     rcx, [rcx+10h]
0x18003f019  test    rbx, rbx
0x18003f01c  mov     rdx, rbx
0x18003f01f  mov     rax, rdi
0x18003f022  cmovz   rdx, r9
0x18003f026  cmp     r8, 0
0x18003f02a  mov     [r11-60h], rdx
0x18003f02e  cmovz   r8, r9
0x18003f032  test    rdi, rdi
0x18003f035  mov     [r11-68h], r8
0x18003f039  cmovz   rax, r9
0x18003f03d  mov     r9d, r14d
0x18003f040  mov     [r11-70h], rax
0x18003f044  mov     [r11-78h], r15d
0x18003f048  mov     [r11-80h], r12d
0x18003f04c  mov     [rsp+0A8h+var_88], ebp
0x18003f050  call    WPP_SF_DDDDSSS
0x18003f055  lea     rcx, AppInfo_PerfTrack_Elevation_AxIS_Start; struct _EVENT_DESCRIPTOR *
0x18003f05c  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003f061  mov     rcx, [rsp+0A8h+Source]; Source
0x18003f069  lea     r8, [rsp+0A8h+hMem]; struct _CONSENTUI_PARAM_HEADER **
0x18003f06e  mov     rdx, rbx; wchar_t *
0x18003f071  mov     [rsp+0A8h+var_34], eax
0x18003f075  call    ?AiBuildAxISParams@@YAKPEBG0PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildAxISParams(ushort const *,ushort const *,_CONSENTUI_PARAM_HEADER * *)
0x18003f07a  mov     rbx, [rsp+0A8h+hMem]
0x18003f07f  xor     ecx, ecx
0x18003f081  mov     [rsp+0A8h+Reply], eax
0x18003f085  test    eax, eax
0x18003f087  jnz     short loc_18003F0E5
0x18003f089  mov     eax, [rsp+0A8h+var_34]
0x18003f08d  mov     r9d, ebp; unsigned int
0x18003f090  mov     rdx, [rsp+0A8h+arg_8]; void *
0x18003f098  mov     r8, r14; unsigned __int64
0x18003f09b  mov     [rsp+0A8h+var_40], rcx; int *
0x18003f0a0  mov     [rsp+0A8h+var_48], rcx; enum UACPROMPT_POLICY *
0x18003f0a5  mov     [rsp+0A8h+var_50], rcx; char *
0x18003f0aa  mov     [rsp+0A8h+var_58], ecx; unsigned int
0x18003f0ae  mov     [rbx+34h], eax
0x18003f0b1  mov     rax, [rsp+0A8h+arg_48]
0x18003f0b9  mov     [rsp+0A8h+var_60], rax; unsigned __int64 *
0x18003f0be  mov     [rsp+0A8h+var_68], rcx; unsigned __int16 *
0x18003f0c3  mov     ecx, 2; unsigned int
0x18003f0c8  mov     [rsp+0A8h+var_70], r15d; unsigned int
0x18003f0cd  mov     [rsp+0A8h+var_78], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003f0d2  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18003f0d7  mov     [rsp+0A8h+var_88], r12d; int
0x18003f0dc  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003f0e1  mov     [rsp+0A8h+Reply], eax
0x18003f0e5  mov     rcx, rbx; hMem
0x18003f0e8  call    cs:__imp_LocalFree
0x18003f0ef  nop     dword ptr [rax+rax+00h]
0x18003f0f4  lea     rdx, [rsp+0A8h+Reply]; Reply
0x18003f0f9  mov     rcx, r13; pAsync
0x18003f0fc  call    cs:__imp_RpcAsyncCompleteCall
0x18003f103  nop     dword ptr [rax+rax+00h]
0x18003f108  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f10f  lea     rax, WPP_GLOBAL_Control
0x18003f116  cmp     rcx, rax
0x18003f119  jz      short loc_18003F13B
0x18003f11b  test    byte ptr [rcx+1Ch], 1
0x18003f11f  jz      short loc_18003F13B
0x18003f121  mov     r9d, [rsp+0A8h+Reply]
0x18003f126  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003f12d  mov     rcx, [rcx+10h]
0x18003f131  mov     edx, 11h
0x18003f136  call    WPP_SF_D
0x18003f13b  lea     r11, [rsp+0A8h+var_28]
0x18003f143  mov     rbx, [r11+30h]
0x18003f147  mov     rbp, [r11+40h]
0x18003f14b  mov     rsp, r11
0x18003f14e  pop     r15
0x18003f150  pop     r14
0x18003f152  pop     r13
0x18003f154  pop     r12
0x18003f156  pop     rdi
0x18003f157  retn
```
