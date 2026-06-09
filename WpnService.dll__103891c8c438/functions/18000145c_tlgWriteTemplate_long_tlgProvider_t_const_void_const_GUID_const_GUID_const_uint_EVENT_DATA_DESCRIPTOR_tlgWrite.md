# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000145c`
- end: `0x1800015e7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapSz@G@@54@Z`
- size: `395`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64, __int64, int **, int **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033520`

## callees

- `0x18000145c`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800015c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800015c4`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int **a9,
        int **a10,
        __int64 a11)
{
  __int64 v14; // rcx
  int *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  int *v18; // rdx
  int v19; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v23; // [rsp+60h] [rbp-71h]
  int v24; // [rsp+68h] [rbp-69h]
  int v25; // [rsp+6Ch] [rbp-65h]
  __int64 v26; // [rsp+70h] [rbp-61h]
  __int64 v27; // [rsp+78h] [rbp-59h]
  __int64 v28; // [rsp+80h] [rbp-51h]
  __int64 v29; // [rsp+88h] [rbp-49h]
  __int64 v30; // [rsp+90h] [rbp-41h]
  __int64 v31; // [rsp+98h] [rbp-39h]
  __int64 v32; // [rsp+A0h] [rbp-31h]
  __int64 v33; // [rsp+A8h] [rbp-29h]
  int *v34; // [rsp+B0h] [rbp-21h]
  int v35; // [rsp+B8h] [rbp-19h]
  int v36; // [rsp+BCh] [rbp-15h]
  int *v37; // [rsp+C0h] [rbp-11h]
  int v38; // [rsp+C8h] [rbp-9h]
  int v39; // [rsp+CCh] [rbp-5h]
  __int64 v40; // [rsp+D0h] [rbp-1h]
  __int64 v41; // [rsp+D8h] [rbp+7h]

  v40 = a11;
  v41 = 4;
  v14 = -1;
  v15 = *a10;
  if ( *a10 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &dword_18003A074;
    v17 = 2;
  }
  v38 = v17;
  v37 = v15;
  v39 = 0;
  v18 = *a9;
  if ( *a9 )
  {
    do
      ++v14;
    while ( *((_WORD *)v18 + v14) );
    v19 = 2 * v14 + 2;
  }
  else
  {
    v18 = &dword_18003A074;
    v19 = 2;
  }
  v32 = a8;
  v30 = a7;
  v28 = a6;
  v26 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v35 = v19;
  v34 = v18;
  v36 = 0;
  v33 = 8;
  v31 = 4;
  v29 = 4;
  v27 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v24 = *(unsigned __int16 *)(a2 + 11);
  v23 = a2 + 11;
  UserData.Reserved = 2;
  v25 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 9u, &UserData);
}

```

## disassembly

```asm
0x18000145c  mov     [rsp-8+arg_8], rbx
0x180001461  push    rbp
0x180001462  lea     rbp, [rsp-1Fh]
0x180001467  sub     rsp, 0F0h
0x18000146e  mov     rax, cs:__security_cookie
0x180001475  xor     rax, rsp
0x180001478  mov     [rbp+1Fh+var_10], rax
0x18000147c  mov     rax, [rbp+1Fh+arg_50]
0x180001480  mov     r11, r8
0x180001483  mov     [rbp+1Fh+var_20], rax
0x180001487  mov     r8, rdx
0x18000148a  mov     rax, [rbp+1Fh+arg_48]
0x18000148e  mov     r10, rcx
0x180001491  xor     ebx, ebx
0x180001493  mov     [rbp+1Fh+var_18], 4
0x18000149b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000149f  mov     rdx, [rax]
0x1800014a2  test    rdx, rdx
0x1800014a5  jz      short loc_1800014BC
0x1800014a7  mov     rax, rcx
0x1800014aa  inc     rax
0x1800014ad  cmp     [rdx+rax*2], bx
0x1800014b1  jnz     short loc_1800014AA
0x1800014b3  lea     eax, ds:2[rax*2]
0x1800014ba  jmp     short loc_1800014C8
0x1800014bc  lea     rdx, dword_18003A074
0x1800014c3  mov     eax, 2
0x1800014c8  mov     [rbp+1Fh+var_28], eax
0x1800014cb  mov     rax, [rbp+1Fh+arg_40]
0x1800014cf  mov     [rbp+1Fh+var_30], rdx
0x1800014d3  mov     [rbp+1Fh+var_24], ebx
0x1800014d6  mov     rdx, [rax]
0x1800014d9  test    rdx, rdx
0x1800014dc  jz      short loc_1800014F0
0x1800014de  inc     rcx
0x1800014e1  cmp     [rdx+rcx*2], bx
0x1800014e5  jnz     short loc_1800014DE
0x1800014e7  lea     ecx, ds:2[rcx*2]
0x1800014ee  jmp     short loc_1800014FC
0x1800014f0  lea     rdx, dword_18003A074
0x1800014f7  mov     ecx, 2
0x1800014fc  mov     rax, [rbp+1Fh+arg_38]
0x180001500  mov     [rbp+1Fh+var_50], rax
0x180001504  mov     rax, [rbp+1Fh+arg_30]
0x180001508  mov     [rbp+1Fh+var_60], rax
0x18000150c  mov     rax, [rbp+1Fh+arg_28]
0x180001510  mov     [rbp+1Fh+var_70], rax
0x180001514  mov     rax, [rbp+1Fh+arg_20]
0x180001518  mov     [rbp+1Fh+var_80], rax
0x18000151c  movzx   eax, byte ptr [r8]
0x180001520  shl     eax, 18h
0x180001523  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x180001527  movzx   eax, word ptr [r8+1]
0x18000152c  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x180001530  mov     rax, [r8+3]
0x180001534  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x180001539  mov     rax, [r10+8]
0x18000153d  mov     [rsp+0F0h+var_A0.Ptr], rax
0x180001542  mov     [rbp+1Fh+var_38], ecx
0x180001545  lea     rcx, [r8+0Bh]
0x180001549  mov     [rbp+1Fh+var_40], rdx
0x18000154d  mov     r8, r11; ActivityId
0x180001550  mov     [rbp+1Fh+var_34], ebx
0x180001553  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x180001558  mov     [rbp+1Fh+var_48], 8
0x180001560  mov     [rbp+1Fh+var_58], 4
0x180001568  mov     [rbp+1Fh+var_68], 4
0x180001570  mov     [rbp+1Fh+var_78], 8
0x180001578  movzx   eax, word ptr [rax]
0x18000157b  mov     [rbp+1Fh+var_A0.Size], eax
0x18000157e  movzx   eax, word ptr [rcx]
0x180001581  mov     [rbp+1Fh+var_88], eax
0x180001584  lea     rax, _TraceLoggingMetadataEnd
0x18000158b  mov     [rbp+1Fh+var_90], rcx
0x18000158f  lea     rcx, _TraceLoggingMetadata
0x180001596  sub     eax, ecx
0x180001598  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x18000159f  mov     [rbp+1Fh+var_84], 1
0x1800015a6  mov     [rsp+0F0h+var_C0], eax
0x1800015aa  mov     eax, [rsp+0F0h+var_C0]
0x1800015ae  mov     rcx, [r10+20h]; RegHandle
0x1800015b2  lea     rax, [rsp+0F0h+var_A0]
0x1800015b7  mov     [rsp+0F0h+UserData], rax; UserData
0x1800015bc  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x1800015c4  call    cs:__imp_EventWriteTransfer
0x1800015ca  mov     rcx, [rbp+1Fh+var_10]
0x1800015ce  xor     rcx, rsp; StackCookie
0x1800015d1  call    __security_check_cookie
0x1800015d6  mov     rbx, [rsp+0F0h+arg_8]
0x1800015de  add     rsp, 0F0h
0x1800015e5  pop     rbp
0x1800015e6  retn
```
