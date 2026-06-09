# RAiGetTokenForAxIS

- ea: `0x180041c00`
- end: `0x180041db7`
- name: `RAiGetTokenForAxIS`
- size: `439`
- prototype: `_UNKNOWN **__fastcall(PRPC_ASYNC_STATE pAsync, void *, __int64, unsigned int, int, unsigned __int16 *, wchar_t *Source, wchar_t *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180026f40`
- `0x180027668`
- `0x180028938`
- `0x180040d64`
- `0x180041c00`
- `0x180042cac`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180041d61`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180041d61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041d53`

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
  const wchar_t *v13; // r8
  const wchar_t *v14; // r10
  const wchar_t *v15; // rax
  unsigned int v16; // eax
  struct _CONSENTUI_PARAM_HEADER *v17; // rbx
  _UNKNOWN **result; // rax
  unsigned int Reply; // [rsp+70h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+74h] [rbp-34h]
  HLOCAL hMem; // [rsp+78h] [rbp-30h] BYREF

  Reply = 0;
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
      (unsigned int)L"NULL",
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
                          WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x180041c00  mov     r11, rsp
0x180041c03  mov     [r11+8], rbx
0x180041c07  mov     [r11+18h], rbp
0x180041c0b  mov     [r11+10h], rdx
0x180041c0f  push    rdi
0x180041c10  push    r12
0x180041c12  push    r13
0x180041c14  push    r14
0x180041c16  push    r15
0x180041c18  sub     rsp, 80h
0x180041c1f  mov     ebp, r9d
0x180041c22  mov     [rsp+0A8h+Reply], 0
0x180041c2a  mov     r14, r8
0x180041c2d  mov     qword ptr [r11-30h], 0
0x180041c35  mov     r13, rcx
0x180041c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c3f  lea     rax, WPP_GLOBAL_Control
0x180041c46  mov     r15d, [rsp+0A8h+arg_40]
0x180041c4e  mov     rbx, [rsp+0A8h+arg_38]
0x180041c56  mov     rdi, [rsp+0A8h+arg_28]
0x180041c5e  mov     r12d, [rsp+0A8h+arg_20]
0x180041c66  cmp     rcx, rax
0x180041c69  jz      short loc_180041CC0
0x180041c6b  test    byte ptr [rcx+1Ch], 1
0x180041c6f  jz      short loc_180041CC0
0x180041c71  mov     r8, [rsp+0A8h+Source]
0x180041c79  lea     rdx, aNull_0; "NULL"
0x180041c80  mov     rcx, [rcx+10h]
0x180041c84  test    rbx, rbx
0x180041c87  mov     r10, rbx
0x180041c8a  mov     rax, rdi
0x180041c8d  cmovz   r10, rdx
0x180041c91  mov     r9d, r14d
0x180041c94  mov     [r11-60h], r10
0x180041c98  cmp     r8, 0
0x180041c9c  cmovz   r8, rdx
0x180041ca0  test    rdi, rdi
0x180041ca3  mov     [r11-68h], r8
0x180041ca7  cmovz   rax, rdx
0x180041cab  mov     [r11-70h], rax
0x180041caf  mov     [r11-78h], r15d
0x180041cb3  mov     [r11-80h], r12d
0x180041cb7  mov     [rsp+0A8h+var_88], ebp
0x180041cbb  call    WPP_SF_DDDDSSS
0x180041cc0  lea     rcx, AppInfo_PerfTrack_Elevation_AxIS_Start; struct _EVENT_DESCRIPTOR *
0x180041cc7  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x180041ccc  mov     rcx, [rsp+0A8h+Source]; Source
0x180041cd4  lea     r8, [rsp+0A8h+hMem]; struct _CONSENTUI_PARAM_HEADER **
0x180041cd9  mov     rdx, rbx; wchar_t *
0x180041cdc  mov     [rsp+0A8h+var_34], eax
0x180041ce0  call    ?AiBuildAxISParams@@YAKPEBG0PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildAxISParams(ushort const *,ushort const *,_CONSENTUI_PARAM_HEADER * *)
0x180041ce5  mov     rbx, [rsp+0A8h+hMem]
0x180041cea  xor     ecx, ecx
0x180041cec  mov     [rsp+0A8h+Reply], eax
0x180041cf0  test    eax, eax
0x180041cf2  jnz     short loc_180041D50
0x180041cf4  mov     eax, [rsp+0A8h+var_34]
0x180041cf8  mov     r9d, ebp; unsigned int
0x180041cfb  mov     rdx, [rsp+0A8h+arg_8]; void *
0x180041d03  mov     r8, r14; unsigned __int64
0x180041d06  mov     [rsp+0A8h+var_40], rcx; int *
0x180041d0b  mov     [rsp+0A8h+var_48], rcx; enum UACPROMPT_POLICY *
0x180041d10  mov     [rsp+0A8h+var_50], rcx; char *
0x180041d15  mov     [rsp+0A8h+var_58], ecx; unsigned int
0x180041d19  mov     [rbx+34h], eax
0x180041d1c  mov     rax, [rsp+0A8h+arg_48]
0x180041d24  mov     [rsp+0A8h+var_60], rax; unsigned __int64 *
0x180041d29  mov     [rsp+0A8h+var_68], rcx; unsigned __int16 *
0x180041d2e  mov     ecx, 2; unsigned int
0x180041d33  mov     [rsp+0A8h+var_70], r15d; unsigned int
0x180041d38  mov     [rsp+0A8h+var_78], rbx; struct _CONSENTUI_PARAM_HEADER *
0x180041d3d  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x180041d42  mov     [rsp+0A8h+var_88], r12d; int
0x180041d47  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x180041d4c  mov     [rsp+0A8h+Reply], eax
0x180041d50  mov     rcx, rbx; hMem
0x180041d53  call    cs:__imp_LocalFree
0x180041d59  lea     rdx, [rsp+0A8h+Reply]; Reply
0x180041d5e  mov     rcx, r13; pAsync
0x180041d61  call    cs:__imp_RpcAsyncCompleteCall
0x180041d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d6e  lea     rax, WPP_GLOBAL_Control
0x180041d75  cmp     rcx, rax
0x180041d78  jz      short loc_180041D9A
0x180041d7a  test    byte ptr [rcx+1Ch], 1
0x180041d7e  jz      short loc_180041D9A
0x180041d80  mov     r9d, [rsp+0A8h+Reply]
0x180041d85  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x180041d8c  mov     rcx, [rcx+10h]
0x180041d90  mov     edx, 11h
0x180041d95  call    WPP_SF_D
0x180041d9a  lea     r11, [rsp+0A8h+var_28]
0x180041da2  mov     rbx, [r11+30h]
0x180041da6  mov     rbp, [r11+40h]
0x180041daa  mov     rsp, r11
0x180041dad  pop     r15
0x180041daf  pop     r14
0x180041db1  pop     r13
0x180041db3  pop     r12
0x180041db5  pop     rdi
0x180041db6  retn
```
