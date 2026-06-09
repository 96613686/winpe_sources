# CDShowMPEG2Demux::GetPages(tagCAUUID *)

- ea: `0x180014d40`
- end: `0x180014de7`
- name: `?GetPages@CDShowMPEG2Demux@@UEAAJPEAUtagCAUUID@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(CDShowMPEG2Demux *__hidden this, struct tagCAUUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180014d40`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180014d96`
- `ole32!CoTaskMemAlloc` at `0x180014d96`

## pseudocode

```c
__int64 __fastcall CDShowMPEG2Demux::GetPages(CDShowMPEG2Demux *this, struct tagCAUUID *a2)
{
  __int64 v4; // rbx
  ULONG v5; // eax
  GUID *v6; // rax
  GUID v7; // xmm0

  if ( !a2 )
    return 2147500035LL;
  v4 = *(_QWORD *)(*((_QWORD *)this + 2) + 336LL);
  if ( v4 && (LODWORD(v4) = *(_DWORD *)(v4 + 128), (_DWORD)v4) && (unsigned int)(v4 - 1) <= 1 )
    v5 = 2;
  else
    v5 = 1;
  a2->cElems = v5;
  v6 = (GUID *)CoTaskMemAlloc(16LL * v5);
  a2->pElems = v6;
  if ( !v6 )
    return 2147942414LL;
  *v6 = CLSID_MPEG2DemuxPropOutputPins;
  if ( (_DWORD)v4 == 1 )
  {
    v7 = CLSID_MPEG2DemuxPropPIDMap;
LABEL_14:
    a2->pElems[1] = v7;
    return 0;
  }
  if ( (_DWORD)v4 == 2 )
  {
    v7 = CLSID_MPEG2DemuxPropStreamIdMap;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180014d40  mov     [rsp+arg_0], rbx
0x180014d45  push    rdi
0x180014d46  sub     rsp, 20h
0x180014d4a  mov     rdi, rdx
0x180014d4d  test    rdx, rdx
0x180014d50  jnz     short loc_180014D5C
0x180014d52  mov     eax, 80004003h
0x180014d57  jmp     loc_180014DDC
0x180014d5c  mov     rax, [rcx+10h]
0x180014d60  mov     rbx, [rax+150h]
0x180014d67  test    rbx, rbx
0x180014d6a  jz      short loc_180014D89
0x180014d6c  mov     ebx, [rbx+80h]
0x180014d72  mov     eax, ebx
0x180014d74  test    ebx, ebx
0x180014d76  jz      short loc_180014D89
0x180014d78  sub     eax, 1
0x180014d7b  jz      short loc_180014D82
0x180014d7d  cmp     eax, 1
0x180014d80  jnz     short loc_180014D89
0x180014d82  mov     eax, 2
0x180014d87  jmp     short loc_180014D8E
0x180014d89  mov     eax, 1
0x180014d8e  mov     ecx, eax
0x180014d90  shl     rcx, 4; cb
0x180014d94  mov     [rdx], eax
0x180014d96  call    cs:__imp_CoTaskMemAlloc
0x180014d9c  mov     [rdi+8], rax
0x180014da0  test    rax, rax
0x180014da3  jnz     short loc_180014DAC
0x180014da5  mov     eax, 8007000Eh
0x180014daa  jmp     short loc_180014DDC
0x180014dac  movups  xmm0, xmmword ptr cs:CLSID_MPEG2DemuxPropOutputPins.Data1
0x180014db3  movdqu  xmmword ptr [rax], xmm0
0x180014db7  cmp     ebx, 1
0x180014dba  jnz     short loc_180014DC5
0x180014dbc  movups  xmm0, xmmword ptr cs:CLSID_MPEG2DemuxPropPIDMap.Data1
0x180014dc3  jmp     short loc_180014DD1
0x180014dc5  cmp     ebx, 2
0x180014dc8  jnz     short loc_180014DDA
0x180014dca  movups  xmm0, xmmword ptr cs:CLSID_MPEG2DemuxPropStreamIdMap.Data1
0x180014dd1  mov     rax, [rdi+8]
0x180014dd5  movdqu  xmmword ptr [rax+10h], xmm0
0x180014dda  xor     eax, eax
0x180014ddc  mov     rbx, [rsp+28h+arg_0]
0x180014de1  add     rsp, 20h
0x180014de5  pop     rdi
0x180014de6  retn
```
