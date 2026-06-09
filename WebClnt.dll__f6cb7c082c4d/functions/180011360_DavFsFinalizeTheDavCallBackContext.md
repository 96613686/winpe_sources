# DavFsFinalizeTheDavCallBackContext

- ea: `0x180011360`
- end: `0x1800113c2`
- name: `DavFsFinalizeTheDavCallBackContext`
- size: `98`
- prototype: `void __fastcall(__int64)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce10`
- `0x1800169d4`
- `0x18001ca70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180021c54`
- `0x180023360`
- `0x180023960`
- `0x180024190`

## callees

- `0x18000b7dc`
- `0x180011360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001137d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001137d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011373`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011373`

## pseudocode

```c
void __fastcall DavFsFinalizeTheDavCallBackContext(__int64 a1)
{
  void *v2; // rcx
  DWORD LastError; // eax

  v2 = *(void **)(a1 + 72);
  if ( v2 != (void *)-1LL )
  {
    if ( !CloseHandle(v2) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
    }
    *(_QWORD *)(a1 + 72) = -1;
  }
}

```

## disassembly

```asm
0x180011360  push    rbx
0x180011362  sub     rsp, 20h
0x180011366  mov     rbx, rcx
0x180011369  mov     rcx, [rcx+48h]; hObject
0x18001136d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011371  jz      short loc_1800113BC
0x180011373  call    cs:__imp_CloseHandle
0x180011379  test    eax, eax
0x18001137b  jnz     short loc_1800113B4
0x18001137d  call    cs:__imp_GetLastError
0x180011383  mov     rcx, cs:WPP_GLOBAL_Control
0x18001138a  lea     rdx, WPP_GLOBAL_Control
0x180011391  cmp     rcx, rdx
0x180011394  jz      short loc_1800113B4
0x180011396  test    byte ptr [rcx+1Ch], 1
0x18001139a  jz      short loc_1800113B4
0x18001139c  mov     rcx, [rcx+10h]
0x1800113a0  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800113a7  mov     edx, 84h
0x1800113ac  mov     r9d, eax
0x1800113af  call    WPP_SF_d
0x1800113b4  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1800113bc  add     rsp, 20h
0x1800113c0  pop     rbx
0x1800113c1  retn
```
