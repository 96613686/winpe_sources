# CfpReleaseProtectedHandle

- ea: `0x180004a68`
- end: `0x180004aaf`
- name: `CfpReleaseProtectedHandle`
- size: `71`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004460`
- `0x18000d560`
- `0x18000daa0`
- `0x18000deb0`
- `0x18000e020`
- `0x18000e2c0`
- `0x18000e460`
- `0x18000e610`
- `0x180011e18`

## callees

- `0x180004a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004aa4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004aa4`

## pseudocode

```c
void __fastcall CfpReleaseProtectedHandle(__int64 a1)
{
  unsigned __int64 v1; // rcx
  signed __int64 v2; // rax
  __int64 v3; // rtt

  if ( a1 != -1 && (a1 & 1) != 0 )
  {
    v1 = a1 & 0xFFFFFFFFFFFFFFFEuLL;
    do
    {
      v2 = *(_QWORD *)(v1 + 16);
      if ( v2 < 2 )
        break;
      v3 = *(_QWORD *)(v1 + 16);
      if ( v3 == _InterlockedCompareExchange64((volatile signed __int64 *)(v1 + 16), v2 - 2, v2) )
      {
        if ( v2 == 2 )
          SetEvent(*(HANDLE *)(v1 + 8));
        return;
      }
    }
    while ( v2 != 2 );
  }
}

```

## disassembly

```asm
0x180004a68  sub     rsp, 28h
0x180004a6c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004a70  jz      short loc_180004AAA
0x180004a72  test    cl, 1
0x180004a75  jz      short loc_180004AAA
0x180004a77  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180004a7b  mov     rax, [rcx+10h]
0x180004a7f  cmp     rax, 2
0x180004a83  jl      short loc_180004AAA
0x180004a85  lea     rdx, [rax-2]
0x180004a89  lock cmpxchg [rcx+10h], rdx
0x180004a8f  jz      short loc_180004A9B
0x180004a91  test    rdx, rdx
0x180004a94  jnz     short loc_180004A7B
0x180004a96  add     rsp, 28h
0x180004a9a  retn
0x180004a9b  test    rdx, rdx
0x180004a9e  jnz     short loc_180004AAA
0x180004aa0  mov     rcx, [rcx+8]; hEvent
0x180004aa4  call    cs:__imp_SetEvent
0x180004aaa  add     rsp, 28h
0x180004aae  retn
```
