# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180014434`
- end: `0x1800145d3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U3@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@5444@Z`
- size: `415`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, __int64, __int64, __int64, int **, int **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004104`

## callees

- `0x180014434`
- `0x180026200`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800145b0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800145b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int **a8,
        int **a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  __int64 v15; // rcx
  int *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  int *v19; // rdx
  int v20; // ecx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-B1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int8 *v24; // [rsp+60h] [rbp-89h]
  int v25; // [rsp+68h] [rbp-81h]
  int v26; // [rsp+6Ch] [rbp-7Dh]
  __int64 v27; // [rsp+70h] [rbp-79h]
  __int64 v28; // [rsp+78h] [rbp-71h]
  __int64 v29; // [rsp+80h] [rbp-69h]
  __int64 v30; // [rsp+88h] [rbp-61h]
  __int64 v31; // [rsp+90h] [rbp-59h]
  __int64 v32; // [rsp+98h] [rbp-51h]
  int *v33; // [rsp+A0h] [rbp-49h]
  int v34; // [rsp+A8h] [rbp-41h]
  int v35; // [rsp+ACh] [rbp-3Dh]
  int *v36; // [rsp+B0h] [rbp-39h]
  int v37; // [rsp+B8h] [rbp-31h]
  int v38; // [rsp+BCh] [rbp-2Dh]
  __int64 v39; // [rsp+C0h] [rbp-29h]
  __int64 v40; // [rsp+C8h] [rbp-21h]
  __int64 v41; // [rsp+D0h] [rbp-19h]
  __int64 v42; // [rsp+D8h] [rbp-11h]
  __int64 v43; // [rsp+E0h] [rbp-9h]
  __int64 v44; // [rsp+E8h] [rbp-1h]

  v43 = a12;
  v41 = a11;
  v15 = -1;
  v39 = a10;
  v44 = 4;
  v42 = 4;
  v40 = 4;
  v16 = *a9;
  if ( *a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = &dword_18003A074;
    v18 = 2;
  }
  v37 = v18;
  v36 = v16;
  v38 = 0;
  v19 = *a8;
  if ( *a8 )
  {
    do
      ++v15;
    while ( *((_WORD *)v19 + v15) );
    v20 = 2 * v15 + 2;
  }
  else
  {
    v19 = &dword_18003A074;
    v20 = 2;
  }
  v31 = a7;
  v29 = a6;
  v27 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v34 = v20;
  v33 = v19;
  v35 = 0;
  v32 = 8;
  v30 = 4;
  v28 = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v25 = *(unsigned __int16 *)(a2 + 11);
  v24 = a2 + 11;
  UserData.Reserved = 2;
  v26 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 0xAu, &UserData);
}

```

## disassembly

```asm
0x180014434  mov     [rsp-8+arg_8], rbx
0x180014439  push    rbp
0x18001443a  lea     rbp, [rsp-17h]
0x18001443f  sub     rsp, 100h
0x180014446  mov     rax, cs:__security_cookie
0x18001444d  xor     rax, rsp
0x180014450  mov     [rbp+17h+var_10], rax
0x180014454  mov     rax, [rbp+17h+arg_58]
0x180014458  mov     r11, r8
0x18001445b  mov     [rbp+17h+var_20], rax
0x18001445f  mov     r8, rdx
0x180014462  mov     rax, [rbp+17h+arg_50]
0x180014466  mov     r10, rcx
0x180014469  mov     [rbp+17h+var_30], rax
0x18001446d  xor     ebx, ebx
0x18001446f  mov     rax, [rbp+17h+arg_48]
0x180014473  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180014477  mov     [rbp+17h+var_40], rax
0x18001447b  mov     rax, [rbp+17h+arg_40]
0x18001447f  mov     [rbp+17h+var_18], 4
0x180014487  mov     [rbp+17h+var_28], 4
0x18001448f  mov     [rbp+17h+var_38], 4
0x180014497  mov     rdx, [rax]
0x18001449a  test    rdx, rdx
0x18001449d  jz      short loc_1800144B4
0x18001449f  mov     rax, rcx
0x1800144a2  inc     rax
0x1800144a5  cmp     [rdx+rax*2], bx
0x1800144a9  jnz     short loc_1800144A2
0x1800144ab  lea     eax, ds:2[rax*2]
0x1800144b2  jmp     short loc_1800144C0
0x1800144b4  lea     rdx, dword_18003A074
0x1800144bb  mov     eax, 2
0x1800144c0  mov     [rbp+17h+var_48], eax
0x1800144c3  mov     rax, [rbp+17h+arg_38]
0x1800144c7  mov     [rbp+17h+var_50], rdx
0x1800144cb  mov     [rbp+17h+var_44], ebx
0x1800144ce  mov     rdx, [rax]
0x1800144d1  test    rdx, rdx
0x1800144d4  jz      short loc_1800144E8
0x1800144d6  inc     rcx
0x1800144d9  cmp     [rdx+rcx*2], bx
0x1800144dd  jnz     short loc_1800144D6
0x1800144df  lea     ecx, ds:2[rcx*2]
0x1800144e6  jmp     short loc_1800144F4
0x1800144e8  lea     rdx, dword_18003A074
0x1800144ef  mov     ecx, 2
0x1800144f4  mov     rax, [rbp+17h+arg_30]
0x1800144f8  mov     [rbp+17h+var_70], rax
0x1800144fc  mov     rax, [rbp+17h+arg_28]
0x180014500  mov     [rbp+17h+var_80], rax
0x180014504  mov     rax, [rbp+17h+arg_20]
0x180014508  mov     [rbp+17h+var_90], rax
0x18001450c  movzx   eax, byte ptr [r8]
0x180014510  shl     eax, 18h
0x180014513  mov     dword ptr [rsp+100h+EventDescriptor.Id], eax
0x180014517  movzx   eax, word ptr [r8+1]
0x18001451c  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x180014520  mov     rax, [r8+3]
0x180014524  mov     [rsp+100h+EventDescriptor.Keyword], rax
0x180014529  mov     rax, [r10+8]
0x18001452d  mov     [rsp+100h+var_B0.Ptr], rax
0x180014532  mov     [rbp+17h+var_58], ecx
0x180014535  lea     rcx, [r8+0Bh]
0x180014539  mov     [rbp+17h+var_60], rdx
0x18001453d  mov     r8, r11; ActivityId
0x180014540  mov     [rbp+17h+var_54], ebx
0x180014543  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x180014548  mov     [rbp+17h+var_68], 8
0x180014550  mov     [rbp+17h+var_78], 4
0x180014558  mov     [rbp+17h+var_88], 8
0x180014560  movzx   eax, word ptr [rax]
0x180014563  mov     [rsp+100h+var_B0.Size], eax
0x180014567  movzx   eax, word ptr [rcx]
0x18001456a  mov     [rsp+100h+var_98], eax
0x18001456e  lea     rax, _TraceLoggingMetadataEnd
0x180014575  mov     [rsp+100h+var_A0], rcx
0x18001457a  lea     rcx, _TraceLoggingMetadata
0x180014581  sub     eax, ecx
0x180014583  mov     dword ptr [rsp+100h+var_B0.0Ch], 2
0x18001458b  mov     [rbp+17h+var_94], 1
0x180014592  mov     [rsp+100h+var_D0], eax
0x180014596  mov     eax, [rsp+100h+var_D0]
0x18001459a  mov     rcx, [r10+20h]; RegHandle
0x18001459e  lea     rax, [rsp+100h+var_B0]
0x1800145a3  mov     [rsp+100h+UserData], rax; UserData
0x1800145a8  mov     [rsp+100h+UserDataCount], 0Ah; UserDataCount
0x1800145b0  call    cs:__imp_EventWriteTransfer
0x1800145b6  mov     rcx, [rbp+17h+var_10]
0x1800145ba  xor     rcx, rsp; StackCookie
0x1800145bd  call    __security_check_cookie
0x1800145c2  mov     rbx, [rsp+100h+arg_8]
0x1800145ca  add     rsp, 100h
0x1800145d1  pop     rbp
0x1800145d2  retn
```
