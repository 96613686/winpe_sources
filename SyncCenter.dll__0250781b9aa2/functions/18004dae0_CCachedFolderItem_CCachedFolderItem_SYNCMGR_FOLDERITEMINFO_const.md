# CCachedFolderItem::CCachedFolderItem(SYNCMGR_FOLDERITEMINFO const &)

- ea: `0x18004dae0`
- end: `0x18004dc53`
- name: `??0CCachedFolderItem@@QEAA@AEBUSYNCMGR_FOLDERITEMINFO@@@Z`
- size: `371`
- prototype: `CCachedFolderItem *__fastcall(CCachedFolderItem *__hidden this, const struct SYNCMGR_FOLDERITEMINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004dcc0`

## callees

- `0x18004dae0`
- `0x180052912`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004db78`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004db78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004db6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004db6b`
- `USER32!CopyIcon` at `0x18004db5e`
- `USER32!CopyIcon` at `0x18004db5e`

## pseudocode

```c
CCachedFolderItem *__fastcall CCachedFolderItem::CCachedFolderItem(
        CCachedFolderItem *this,
        const struct SYNCMGR_FOLDERITEMINFO *a2)
{
  HICON v3; // rcx
  CCachedFolderItem *result; // rax

  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &CCachedFolderItem::`vftable';
  memcpy_0((char *)this + 64, a2, 0x550u);
  v3 = (HICON)*((_QWORD *)this + 110);
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_DWORD *)this + 367) = 0;
  *((_DWORD *)this + 368) = 1;
  *((_DWORD *)this + 366) = 1;
  if ( v3 )
    *((_QWORD *)this + 110) = CopyIcon(v3);
  *((_DWORD *)this + 3) = GetTickCount();
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_OWORD *)this + 90) = 0;
  *((_QWORD *)this + 182) = 0;
  *((_QWORD *)this + 185) = (char *)this + 340;
  *((_QWORD *)this + 186) = (char *)this + 68;
  *((_QWORD *)this + 187) = (char *)this + 84;
  *((_QWORD *)this + 188) = (char *)this + 212;
  *((_QWORD *)this + 189) = (char *)this + 852;
  *((_QWORD *)this + 190) = (char *)this + 596;
  *((_QWORD *)this + 191) = (char *)this + 1440;
  *((_QWORD *)this + 192) = (char *)this + 1424;
  *((_QWORD *)this + 193) = (char *)this + 1432;
  *((_QWORD *)this + 194) = (char *)this + 872;
  *((_QWORD *)this + 195) = (char *)this + 868;
  *((_QWORD *)this + 196) = (char *)this + 904;
  *((_QWORD *)this + 197) = (char *)this + 860;
  result = this;
  *((_QWORD *)this + 198) = (char *)this + 1464;
  *((_QWORD *)this + 199) = (char *)this + 1468;
  *((_QWORD *)this + 200) = (char *)this + 1472;
  return result;
}

```

## disassembly

```asm
0x18004dae0  push    rbx
0x18004dae2  push    rbp
0x18004dae3  push    rsi
0x18004dae4  push    rdi
0x18004dae5  push    r12
0x18004dae7  push    r14
0x18004dae9  push    r15
0x18004daeb  sub     rsp, 20h
0x18004daef  lea     rax, ??_7CCachedFolderItem@@6B@; const CCachedFolderItem::`vftable'
0x18004daf6  mov     qword ptr [rcx+8], 1
0x18004dafe  mov     [rcx], rax
0x18004db01  mov     rbx, rcx
0x18004db04  add     rcx, 40h ; '@'; void *
0x18004db08  mov     r8d, 550h; Size
0x18004db0e  xor     r12d, r12d
0x18004db11  call    memcpy_0
0x18004db16  mov     rcx, [rbx+370h]; hIcon
0x18004db1d  lea     rsi, [rbx+590h]
0x18004db24  mov     [rsi], r12
0x18004db27  lea     r14, [rbx+598h]
0x18004db2e  mov     [r14], r12
0x18004db31  lea     rbp, [rbx+5BCh]
0x18004db38  mov     [rbp+0], r12d
0x18004db3c  lea     r12, [rbx+5C0h]
0x18004db43  mov     dword ptr [r12], 1
0x18004db4b  lea     r15, [rbx+5B8h]
0x18004db52  mov     dword ptr [r15], 1
0x18004db59  test    rcx, rcx
0x18004db5c  jz      short loc_18004DB6B
0x18004db5e  call    cs:__imp_CopyIcon
0x18004db64  mov     [rbx+370h], rax
0x18004db6b  call    cs:__imp_GetTickCount
0x18004db71  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004db75  mov     [rbx+0Ch], eax
0x18004db78  call    cs:__imp_InitializeCriticalSection
0x18004db7e  xor     eax, eax
0x18004db80  lea     rcx, [rbx+5A0h]
0x18004db87  xorps   xmm0, xmm0
0x18004db8a  movups  xmmword ptr [rcx], xmm0
0x18004db8d  mov     [rcx+10h], rax
0x18004db91  lea     rax, [rbx+154h]
0x18004db98  mov     [rbx+5C8h], rax
0x18004db9f  lea     rax, [rbx+44h]
0x18004dba3  mov     [rbx+5D0h], rax
0x18004dbaa  lea     rax, [rbx+54h]
0x18004dbae  mov     [rbx+5D8h], rax
0x18004dbb5  lea     rax, [rbx+0D4h]
0x18004dbbc  mov     [rbx+5E0h], rax
0x18004dbc3  lea     rax, [rbx+354h]
0x18004dbca  mov     [rbx+5E8h], rax
0x18004dbd1  lea     rax, [rbx+254h]
0x18004dbd8  mov     [rbx+5F0h], rax
0x18004dbdf  lea     rax, [rbx+368h]
0x18004dbe6  mov     [rbx+5F8h], rcx
0x18004dbed  mov     [rbx+600h], rsi
0x18004dbf4  mov     [rbx+608h], r14
0x18004dbfb  mov     [rbx+610h], rax
0x18004dc02  lea     rax, [rbx+364h]
0x18004dc09  mov     [rbx+618h], rax
0x18004dc10  lea     rax, [rbx+388h]
0x18004dc17  mov     [rbx+620h], rax
0x18004dc1e  lea     rax, [rbx+35Ch]
0x18004dc25  mov     [rbx+628h], rax
0x18004dc2c  mov     rax, rbx
0x18004dc2f  mov     [rbx+630h], r15
0x18004dc36  mov     [rbx+638h], rbp
0x18004dc3d  mov     [rbx+640h], r12
0x18004dc44  add     rsp, 20h
0x18004dc48  pop     r15
0x18004dc4a  pop     r14
0x18004dc4c  pop     r12
0x18004dc4e  pop     rdi
0x18004dc4f  pop     rsi
0x18004dc50  pop     rbp
0x18004dc51  pop     rbx
0x18004dc52  retn
```
