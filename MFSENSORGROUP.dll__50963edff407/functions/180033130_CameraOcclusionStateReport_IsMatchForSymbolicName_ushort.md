# CameraOcclusionStateReport::IsMatchForSymbolicName(ushort *)

- ea: `0x180033130`
- end: `0x1800331cf`
- name: `?IsMatchForSymbolicName@CameraOcclusionStateReport@@UEBA_NPEAG@Z`
- size: `159`
- prototype: `bool(CameraOcclusionStateReport *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180033130`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033156`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033156`

## pseudocode

```c
bool __fastcall CameraOcclusionStateReport::IsMatchForSymbolicName(const WCHAR *this, unsigned __int16 *a2)
{
  if ( a2 )
    return CompareStringOrdinal(a2, -1, this + 32, -1, 1) == 2;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      &WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids,
      this,
      -2147024809);
  if ( byte_18008D62D )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      83,
      &WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids,
      this,
      -2147024809);
  return 0;
}

```

## disassembly

```asm
0x180033130  push    rbx
0x180033132  sub     rsp, 30h
0x180033136  mov     rax, rdx
0x180033139  mov     rbx, rcx
0x18003313c  test    rdx, rdx
0x18003313f  jz      short loc_180033168
0x180033141  or      edx, 0FFFFFFFFh; cchCount1
0x180033144  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18003314c  lea     r8, [rcx+40h]; lpString2
0x180033150  mov     r9d, edx; cchCount2
0x180033153  mov     rcx, rax; lpString1
0x180033156  call    cs:__imp_CompareStringOrdinal
0x18003315c  cmp     eax, 2
0x18003315f  setz    al
0x180033162  add     rsp, 30h
0x180033166  pop     rbx
0x180033167  retn
0x180033168  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003316f  jb      short loc_180033198
0x180033171  mov     rcx, cs:WPP_GLOBAL_Control
0x180033178  lea     r8, WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids
0x18003317f  mov     edx, 52h ; 'R'
0x180033184  mov     [rsp+38h+bIgnoreCase], 80070057h
0x18003318c  mov     r9, rbx
0x18003318f  mov     rcx, [rcx+10h]
0x180033193  call    WPP_SF_qD
0x180033198  cmp     cs:byte_18008D62D, 1
0x18003319f  jb      short loc_1800331CB
0x1800331a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331a8  lea     r8, WPP_70567b7aa3313d2d575f02faf3e844e7_Traceguids
0x1800331af  mov     edx, 53h ; 'S'
0x1800331b4  mov     [rsp+38h+bIgnoreCase], 80070057h
0x1800331bc  mov     r9, rbx
0x1800331bf  mov     rcx, [rcx+0D8h]
0x1800331c6  call    WPP_SF_qD
0x1800331cb  xor     al, al
0x1800331cd  jmp     short loc_180033162
```
