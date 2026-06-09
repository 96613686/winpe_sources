# CMpeg2DemuxMediaSeekingCOM::GetStopPosition(__int64 *)

- ea: `0x180024630`
- end: `0x18002469f`
- name: `?GetStopPosition@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_J@Z`
- size: `111`
- prototype: `int(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024400`
- `0x180024630`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024685`
- `KERNEL32!LeaveCriticalSection` at `0x180024685`
- `KERNEL32!EnterCriticalSection` at `0x18002466d`
- `KERNEL32!EnterCriticalSection` at `0x18002466d`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetStopPosition(CMpeg2DemuxMediaSeekingCOM *this, __int64 *a2)
{
  __int64 v5; // rax
  unsigned int FileStopPosition; // ebx

  if ( !a2 )
    return 2147500035LL;
  v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v5 || !*(_DWORD *)(v5 + 176) )
    return 2147549183LL;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  FileStopPosition = CMpeg2DemuxMediaSeekingCore::GetFileStopPosition(*((CMpeg2DemuxMediaSeekingCore **)this + 6), a2);
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  return FileStopPosition;
}

```

## disassembly

```asm
0x180024630  mov     [rsp+arg_0], rbx
0x180024635  push    rdi
0x180024636  sub     rsp, 20h
0x18002463a  mov     rbx, rdx
0x18002463d  mov     rdi, rcx
0x180024640  test    rdx, rdx
0x180024643  jnz     short loc_18002464C
0x180024645  mov     eax, 80004003h
0x18002464a  jmp     short loc_180024694
0x18002464c  mov     rax, [rcx+30h]
0x180024650  mov     rcx, [rax+28h]
0x180024654  mov     rax, [rcx+150h]
0x18002465b  test    rax, rax
0x18002465e  jz      short loc_18002468F
0x180024660  cmp     dword ptr [rax+0B0h], 0
0x180024667  jz      short loc_18002468F
0x180024669  mov     rcx, [rdi+28h]; lpCriticalSection
0x18002466d  call    cs:__imp_EnterCriticalSection
0x180024673  mov     rcx, [rdi+30h]; this
0x180024677  mov     rdx, rbx; __int64 *
0x18002467a  call    ?GetFileStopPosition@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J@Z; CMpeg2DemuxMediaSeekingCore::GetFileStopPosition(__int64 *)
0x18002467f  mov     rcx, [rdi+28h]; lpCriticalSection
0x180024683  mov     ebx, eax
0x180024685  call    cs:__imp_LeaveCriticalSection
0x18002468b  mov     eax, ebx
0x18002468d  jmp     short loc_180024694
0x18002468f  mov     eax, 8000FFFFh
0x180024694  mov     rbx, [rsp+28h+arg_0]
0x180024699  add     rsp, 20h
0x18002469d  pop     rdi
0x18002469e  retn
```
