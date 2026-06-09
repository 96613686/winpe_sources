# RAiGetTokenForAxIS

- ea: `0x18003f4e0`
- end: `0x18003f699`
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
- `0x18003e5d4`
- `0x18003f4e0`
- `0x18004064c`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f63c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f63c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f628`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f628`

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
0x18003f4e0  mov     r11, rsp
0x18003f4e3  mov     [r11+8], rbx
0x18003f4e7  mov     [r11+18h], rbp
0x18003f4eb  mov     [r11+10h], rdx
0x18003f4ef  push    rdi
0x18003f4f0  push    r12
0x18003f4f2  push    r13
0x18003f4f4  push    r14
0x18003f4f6  push    r15
0x18003f4f8  sub     rsp, 80h
0x18003f4ff  and     qword ptr [r11-30h], 0
0x18003f504  mov     ebp, r9d
0x18003f507  mov     r14, r8
0x18003f50a  mov     r13, rcx
0x18003f50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f514  lea     rax, WPP_GLOBAL_Control
0x18003f51b  mov     r15d, [rsp+0A8h+arg_40]
0x18003f523  mov     rbx, [rsp+0A8h+arg_38]
0x18003f52b  mov     rdi, [rsp+0A8h+arg_28]
0x18003f533  mov     r12d, [rsp+0A8h+arg_20]
0x18003f53b  cmp     rcx, rax
0x18003f53e  jz      short loc_18003F595
0x18003f540  test    byte ptr [rcx+1Ch], 1
0x18003f544  jz      short loc_18003F595
0x18003f546  mov     r8, [rsp+0A8h+Source]
0x18003f54e  lea     r9, aNull_0; "NULL"
0x18003f555  mov     rcx, [rcx+10h]
0x18003f559  test    rbx, rbx
0x18003f55c  mov     rdx, rbx
0x18003f55f  mov     rax, rdi
0x18003f562  cmovz   rdx, r9
0x18003f566  cmp     r8, 0
0x18003f56a  mov     [r11-60h], rdx
0x18003f56e  cmovz   r8, r9
0x18003f572  test    rdi, rdi
0x18003f575  mov     [r11-68h], r8
0x18003f579  cmovz   rax, r9
0x18003f57d  mov     r9d, r14d
0x18003f580  mov     [r11-70h], rax
0x18003f584  mov     [r11-78h], r15d
0x18003f588  mov     [r11-80h], r12d
0x18003f58c  mov     [rsp+0A8h+var_88], ebp
0x18003f590  call    WPP_SF_DDDDSSS
0x18003f595  lea     rcx, AppInfo_PerfTrack_Elevation_AxIS_Start; struct _EVENT_DESCRIPTOR *
0x18003f59c  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003f5a1  mov     rcx, [rsp+0A8h+Source]; Source
0x18003f5a9  lea     r8, [rsp+0A8h+hMem]; struct _CONSENTUI_PARAM_HEADER **
0x18003f5ae  mov     rdx, rbx; wchar_t *
0x18003f5b1  mov     [rsp+0A8h+var_34], eax
0x18003f5b5  call    ?AiBuildAxISParams@@YAKPEBG0PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildAxISParams(ushort const *,ushort const *,_CONSENTUI_PARAM_HEADER * *)
0x18003f5ba  mov     rbx, [rsp+0A8h+hMem]
0x18003f5bf  xor     ecx, ecx
0x18003f5c1  mov     [rsp+0A8h+Reply], eax
0x18003f5c5  test    eax, eax
0x18003f5c7  jnz     short loc_18003F625
0x18003f5c9  mov     eax, [rsp+0A8h+var_34]
0x18003f5cd  mov     r9d, ebp; unsigned int
0x18003f5d0  mov     rdx, [rsp+0A8h+arg_8]; void *
0x18003f5d8  mov     r8, r14; unsigned __int64
0x18003f5db  mov     [rsp+0A8h+var_40], rcx; int *
0x18003f5e0  mov     [rsp+0A8h+var_48], rcx; enum UACPROMPT_POLICY *
0x18003f5e5  mov     [rsp+0A8h+var_50], rcx; char *
0x18003f5ea  mov     [rsp+0A8h+var_58], ecx; unsigned int
0x18003f5ee  mov     [rbx+34h], eax
0x18003f5f1  mov     rax, [rsp+0A8h+arg_48]
0x18003f5f9  mov     [rsp+0A8h+var_60], rax; unsigned __int64 *
0x18003f5fe  mov     [rsp+0A8h+var_68], rcx; unsigned __int16 *
0x18003f603  mov     ecx, 2; unsigned int
0x18003f608  mov     [rsp+0A8h+var_70], r15d; unsigned int
0x18003f60d  mov     [rsp+0A8h+var_78], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003f612  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18003f617  mov     [rsp+0A8h+var_88], r12d; int
0x18003f61c  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003f621  mov     [rsp+0A8h+Reply], eax
0x18003f625  mov     rcx, rbx; hMem
0x18003f628  call    cs:__imp_LocalFree
0x18003f62f  nop     dword ptr [rax+rax+00h]
0x18003f634  lea     rdx, [rsp+0A8h+Reply]; Reply
0x18003f639  mov     rcx, r13; pAsync
0x18003f63c  call    cs:__imp_RpcAsyncCompleteCall
0x18003f643  nop     dword ptr [rax+rax+00h]
0x18003f648  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f64f  lea     rax, WPP_GLOBAL_Control
0x18003f656  cmp     rcx, rax
0x18003f659  jz      short loc_18003F67B
0x18003f65b  test    byte ptr [rcx+1Ch], 1
0x18003f65f  jz      short loc_18003F67B
0x18003f661  mov     r9d, [rsp+0A8h+Reply]
0x18003f666  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003f66d  mov     rcx, [rcx+10h]
0x18003f671  mov     edx, 11h
0x18003f676  call    WPP_SF_D
0x18003f67b  lea     r11, [rsp+0A8h+var_28]
0x18003f683  mov     rbx, [r11+30h]
0x18003f687  mov     rbp, [r11+40h]
0x18003f68b  mov     rsp, r11
0x18003f68e  pop     r15
0x18003f690  pop     r14
0x18003f692  pop     r13
0x18003f694  pop     r12
0x18003f696  pop     rdi
0x18003f697  retn
```
