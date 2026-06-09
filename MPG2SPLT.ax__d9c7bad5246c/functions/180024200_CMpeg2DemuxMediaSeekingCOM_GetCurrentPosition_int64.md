# CMpeg2DemuxMediaSeekingCOM::GetCurrentPosition(__int64 *)

- ea: `0x180024200`
- end: `0x18002426f`
- name: `?GetCurrentPosition@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_J@Z`
- size: `111`
- prototype: `int(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024200`
- `0x180024338`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024255`
- `KERNEL32!LeaveCriticalSection` at `0x180024255`
- `KERNEL32!EnterCriticalSection` at `0x18002423d`
- `KERNEL32!EnterCriticalSection` at `0x18002423d`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetCurrentPosition(CMpeg2DemuxMediaSeekingCOM *this, __int64 *a2)
{
  __int64 v5; // rax
  unsigned int FileStartPosition; // ebx

  if ( !a2 )
    return 2147500035LL;
  v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( !v5 || !*(_DWORD *)(v5 + 176) )
    return 2147549183LL;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  FileStartPosition = CMpeg2DemuxMediaSeekingCore::GetFileStartPosition(*((CMpeg2DemuxMediaSeekingCore **)this + 6), a2);
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
  return FileStartPosition;
}

```

## disassembly

```asm
0x180024200  mov     [rsp+arg_0], rbx
0x180024205  push    rdi
0x180024206  sub     rsp, 20h
0x18002420a  mov     rbx, rdx
0x18002420d  mov     rdi, rcx
0x180024210  test    rdx, rdx
0x180024213  jnz     short loc_18002421C
0x180024215  mov     eax, 80004003h
0x18002421a  jmp     short loc_180024264
0x18002421c  mov     rax, [rcx+30h]
0x180024220  mov     rcx, [rax+28h]
0x180024224  mov     rax, [rcx+150h]
0x18002422b  test    rax, rax
0x18002422e  jz      short loc_18002425F
0x180024230  cmp     dword ptr [rax+0B0h], 0
0x180024237  jz      short loc_18002425F
0x180024239  mov     rcx, [rdi+28h]; lpCriticalSection
0x18002423d  call    cs:__imp_EnterCriticalSection
0x180024243  mov     rcx, [rdi+30h]; this
0x180024247  mov     rdx, rbx; __int64 *
0x18002424a  call    ?GetFileStartPosition@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J@Z; CMpeg2DemuxMediaSeekingCore::GetFileStartPosition(__int64 *)
0x18002424f  mov     rcx, [rdi+28h]; lpCriticalSection
0x180024253  mov     ebx, eax
0x180024255  call    cs:__imp_LeaveCriticalSection
0x18002425b  mov     eax, ebx
0x18002425d  jmp     short loc_180024264
0x18002425f  mov     eax, 8000FFFFh
0x180024264  mov     rbx, [rsp+28h+arg_0]
0x180024269  add     rsp, 20h
0x18002426d  pop     rdi
0x18002426e  retn
```
