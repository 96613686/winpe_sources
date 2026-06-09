# CCachedFolderItem::GetIcon(HICON__ * *)

- ea: `0x18004e070`
- end: `0x18004e0c9`
- name: `?GetIcon@CCachedFolderItem@@UEAAJPEAPEAUHICON__@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(CCachedFolderItem *__hidden this, HICON *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18004e070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e0b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e0b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e090`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e090`
- `USER32!CopyIcon` at `0x18004e0a2`
- `USER32!CopyIcon` at `0x18004e0a2`

## pseudocode

```c
_BOOL8 __fastcall CCachedFolderItem::GetIcon(CCachedFolderItem *this, HICON *a2)
{
  BOOL v4; // edi
  HICON v5; // rcx
  HICON v6; // rax

  *a2 = 0;
  v4 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (HICON)*((_QWORD *)this + 110);
  if ( v5 )
  {
    v6 = CopyIcon(v5);
    *a2 = v6;
    v4 = v6 == 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v4;
}

```

## disassembly

```asm
0x18004e070  push    rbx
0x18004e072  push    rsi
0x18004e073  push    rdi
0x18004e074  push    r14
0x18004e076  sub     rsp, 28h
0x18004e07a  mov     rbx, rcx
0x18004e07d  mov     qword ptr [rdx], 0
0x18004e084  add     rcx, 18h; lpCriticalSection
0x18004e088  mov     r14, rdx
0x18004e08b  mov     edi, 1
0x18004e090  call    cs:__imp_EnterCriticalSection
0x18004e096  mov     rcx, [rbx+370h]; hIcon
0x18004e09d  test    rcx, rcx
0x18004e0a0  jz      short loc_18004E0B3
0x18004e0a2  call    cs:__imp_CopyIcon
0x18004e0a8  xor     edx, edx
0x18004e0aa  mov     [r14], rax
0x18004e0ad  test    rax, rax
0x18004e0b0  cmovnz  edi, edx
0x18004e0b3  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004e0b7  call    cs:__imp_LeaveCriticalSection
0x18004e0bd  mov     eax, edi
0x18004e0bf  add     rsp, 28h
0x18004e0c3  pop     r14
0x18004e0c5  pop     rdi
0x18004e0c6  pop     rsi
0x18004e0c7  pop     rbx
0x18004e0c8  retn
```
