# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(_GUID const &)

- ea: `0x180098fe4`
- end: `0x1800990cc`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `232`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009d730`
- `0x18009d810`
- `0x18009d8a0`
- `0x18009d980`
- `0x18009dbf0`
- `0x18009dcf0`
- `0x18009dd80`
- `0x18009de10`

## callees

- `0x180098fe4`
- `0x1800994fc`
- `0x18009e6d0`
- `0x1800b0460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180099011`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180099011`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(__int64 a1, _DWORD *a2)
{
  PROPVARIANT *Item; // rax
  unsigned int v5; // edi
  __int64 v6; // rbx
  int v7; // edx
  unsigned int v8; // edx

  Item = (PROPVARIANT *)CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, a2);
  v5 = 0;
  v6 = (__int64)Item;
  if ( Item )
  {
    PropVariantClear(Item);
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 60) == v7
      && (int)CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::ExtendStorage(a1, (unsigned int)(2 * v7 + 4)) < 0 )
    {
      return 0;
    }
    else
    {
      v8 = *(_DWORD *)(a1 + 60);
      if ( v8 )
      {
        do
        {
          if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 40LL * v5) >= *a2 )
            break;
          ++v5;
        }
        while ( v5 < v8 );
      }
      memmove(
        (void *)(*(_QWORD *)(a1 + 48) + 40LL * (v5 + 1)),
        (const void *)(*(_QWORD *)(a1 + 48) + 40LL * v5),
        40LL * (v8 - v5));
      *(_OWORD *)(*(_QWORD *)(a1 + 48) + 40LL * v5) = *(_OWORD *)a2;
      v6 = *(_QWORD *)(a1 + 48) + 8 * (5LL * v5 + 2);
      *(_OWORD *)v6 = 0;
      *(_QWORD *)(v6 + 16) = 0;
      ++*(_DWORD *)(a1 + 60);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180098fe4  mov     [rsp+arg_0], rbx
0x180098fe9  mov     [rsp+arg_8], rsi
0x180098fee  mov     [rsp+arg_10], rdi
0x180098ff3  push    r14
0x180098ff5  sub     rsp, 20h
0x180098ff9  mov     r14, rdx
0x180098ffc  mov     rsi, rcx
0x180098fff  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x180099004  xor     edi, edi
0x180099006  mov     rbx, rax
0x180099009  test    rax, rax
0x18009900c  jz      short loc_180099022
0x18009900e  mov     rcx, rax; pvar
0x180099011  call    cs:__imp_PropVariantClear
0x180099018  nop     dword ptr [rax+rax+00h]
0x18009901d  jmp     loc_1800990B2
0x180099022  mov     edx, [rsi+38h]
0x180099025  cmp     [rsi+3Ch], edx
0x180099028  jnz     short loc_180099042
0x18009902a  lea     edx, ds:4[rdx*2]
0x180099031  mov     rcx, rsi
0x180099034  call    ?ExtendStorage@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAJI@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::ExtendStorage(uint)
0x180099039  test    eax, eax
0x18009903b  jns     short loc_180099042
0x18009903d  mov     rbx, rdi
0x180099040  jmp     short loc_1800990B2
0x180099042  mov     edx, [rsi+3Ch]
0x180099045  mov     r10d, [r14]
0x180099048  test    edx, edx
0x18009904a  jz      short loc_180099062
0x18009904c  mov     r9, [rsi+30h]
0x180099050  mov     eax, edi
0x180099052  lea     rcx, [rax+rax*4]
0x180099056  cmp     [r9+rcx*8], r10d
0x18009905a  jnb     short loc_180099062
0x18009905c  inc     edi
0x18009905e  cmp     edi, edx
0x180099060  jb      short loc_180099050
0x180099062  mov     r9, [rsi+30h]
0x180099066  sub     edx, edi
0x180099068  mov     eax, edi
0x18009906a  lea     r8, [rdx+rdx*4]
0x18009906e  lea     rbx, [rax+rax*4]
0x180099072  shl     r8, 3; Size
0x180099076  lea     eax, [rdi+1]
0x180099079  lea     rax, [rax+rax*4]
0x18009907d  lea     rcx, [r9+rax*8]; void *
0x180099081  lea     rdx, [r9+rbx*8]; Src
0x180099085  call    memmove
0x18009908a  movups  xmm0, xmmword ptr [r14]
0x18009908e  mov     rax, [rsi+30h]
0x180099092  movdqu  xmmword ptr [rax+rbx*8], xmm0
0x180099097  mov     rax, [rsi+30h]
0x18009909b  lea     rbx, [rbx+2]
0x18009909f  xorps   xmm0, xmm0
0x1800990a2  lea     rbx, [rax+rbx*8]
0x1800990a6  xor     eax, eax
0x1800990a8  movups  xmmword ptr [rbx], xmm0
0x1800990ab  mov     [rbx+10h], rax
0x1800990af  inc     dword ptr [rsi+3Ch]
0x1800990b2  mov     rsi, [rsp+28h+arg_8]
0x1800990b7  mov     rax, rbx
0x1800990ba  mov     rbx, [rsp+28h+arg_0]
0x1800990bf  mov     rdi, [rsp+28h+arg_10]
0x1800990c4  add     rsp, 20h
0x1800990c8  pop     r14
0x1800990ca  retn
```
