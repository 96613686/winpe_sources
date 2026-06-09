# CMetaData::mdReleaseByRefData(tagCOLRSDATA *)

- ea: `0x180004b30`
- end: `0x180004b88`
- name: `?mdReleaseByRefData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@@Z`
- size: `88`
- prototype: `void __fastcall(CMetaData *__hidden this, struct tagCOLRSDATA *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800026a0`
- `0x180004238`

## callees

- `0x180004b30`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004b61`
- `ole32!CoTaskMemFree` at `0x180004b61`

## pseudocode

```c
void __fastcall CMetaData::mdReleaseByRefData(CMetaData *this, struct tagCOLRSDATA *a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx

  v2 = 0;
  v3 = 0;
  do
  {
    if ( *(_DWORD *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 36)) != 3
      && !*(const struct tagDESIREDCOLUMNS near *const *)((char *)&g_rgDesiredColumn + v3 + 48) )
    {
      CoTaskMemFree(*(LPVOID *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 32)));
      *(_DWORD *)((char *)a2 + *(unsigned int *)((char *)&g_rgDesiredColumn + v3 + 36)) = 3;
    }
    ++v2;
    v3 += 80;
  }
  while ( v2 != 31 );
}

```

## disassembly

```asm
0x180004b30  push    rbx
0x180004b32  push    rbp
0x180004b33  push    rsi
0x180004b34  push    rdi
0x180004b35  sub     rsp, 28h
0x180004b39  xor     edi, edi
0x180004b3b  lea     rbp, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180004b42  xor     ebx, ebx
0x180004b44  mov     rsi, rdx
0x180004b47  mov     eax, [rbx+rbp+24h]
0x180004b4b  cmp     dword ptr [rax+rsi], 3
0x180004b4f  jz      short loc_180004B72
0x180004b51  cmp     qword ptr [rbx+rbp+30h], 0
0x180004b57  jnz     short loc_180004B72
0x180004b59  mov     ecx, [rbx+rbp+20h]
0x180004b5d  mov     rcx, [rcx+rsi]; pv
0x180004b61  call    cs:__imp_CoTaskMemFree
0x180004b67  mov     eax, [rbx+rbp+24h]
0x180004b6b  mov     dword ptr [rax+rsi], 3
0x180004b72  inc     rdi
0x180004b75  add     rbx, 50h ; 'P'
0x180004b79  cmp     rdi, 1Fh
0x180004b7d  jnz     short loc_180004B47
0x180004b7f  add     rsp, 28h
0x180004b83  pop     rdi
0x180004b84  pop     rsi
0x180004b85  pop     rbp
0x180004b86  pop     rbx
0x180004b87  retn
```
