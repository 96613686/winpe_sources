# CfpReferenceProtectedHandle

- ea: `0x180004a10`
- end: `0x180004a60`
- name: `CfpReferenceProtectedHandle`
- size: `80`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004420`
- `0x18000d560`
- `0x18000daa0`
- `0x18000dd60`
- `0x18000deb0`
- `0x18000e020`
- `0x18000e2c0`
- `0x18000e460`
- `0x18000e610`

## callees

- `0x180004a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004a53`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004a53`

## pseudocode

```c
char __fastcall CfpReferenceProtectedHandle(__int64 a1, char a2)
{
  unsigned __int64 v2; // rcx
  signed __int64 v3; // rax
  __int64 v4; // rtt

  if ( a1 == -1 || (a1 & 1) == 0 )
    return 1;
  v2 = a1 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( *(_BYTE *)(v2 + 28) || !a2 )
  {
    do
    {
      v3 = *(_QWORD *)(v2 + 16);
      if ( (v3 & 1) == 0 || v3 + 2 <= v3 )
        break;
      v4 = *(_QWORD *)(v2 + 16);
      if ( v4 == _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 16), v3 + 2, v3) )
      {
        ResetEvent(*(HANDLE *)(v2 + 8));
        return 1;
      }
    }
    while ( v3 != -2 );
  }
  return 0;
}

```

## disassembly

```asm
0x180004a10  sub     rsp, 28h
0x180004a14  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004a18  jz      short loc_180004A59
0x180004a1a  test    cl, 1
0x180004a1d  jz      short loc_180004A59
0x180004a1f  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004a23  cmp     byte ptr [rcx+1Ch], 0
0x180004a27  jnz     short loc_180004A2D
0x180004a29  test    dl, dl
0x180004a2b  jnz     short loc_180004A4B
0x180004a2d  mov     rax, [rcx+10h]
0x180004a31  test    al, 1
0x180004a33  jz      short loc_180004A4B
0x180004a35  lea     rdx, [rax+2]
0x180004a39  cmp     rdx, rax
0x180004a3c  jl      short loc_180004A4B
0x180004a3e  lock cmpxchg [rcx+10h], rdx
0x180004a44  jz      short loc_180004A4F
0x180004a46  test    rdx, rdx
0x180004a49  jnz     short loc_180004A2D
0x180004a4b  xor     al, al
0x180004a4d  jmp     short loc_180004A5B
0x180004a4f  mov     rcx, [rcx+8]; hEvent
0x180004a53  call    cs:__imp_ResetEvent
0x180004a59  mov     al, 1
0x180004a5b  add     rsp, 28h
0x180004a5f  retn
```
