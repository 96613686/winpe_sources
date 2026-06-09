# TFileStream::Create(void *,IStream * *)

- ea: `0x180005588`
- end: `0x180005657`
- name: `?Create@TFileStream@@SAJPEAXPEAPEAUIStream@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, struct IStream **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x180001c48`
- `0x180005588`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800055dd`
- `KERNEL32!GetLastError` at `0x1800055dd`
- `KERNEL32!CloseHandle` at `0x180005645`
- `KERNEL32!CloseHandle` at `0x180005645`
- `KERNEL32!GetCurrentProcess` at `0x1800055a6`
- `KERNEL32!GetCurrentProcess` at `0x1800055af`
- `KERNEL32!GetCurrentProcess` at `0x1800055a6`
- `KERNEL32!GetCurrentProcess` at `0x1800055af`
- `KERNEL32!DuplicateHandle` at `0x1800055d3`
- `KERNEL32!DuplicateHandle` at `0x1800055d3`

## pseudocode

```c
__int64 __fastcall TFileStream::Create(HANDLE hSourceHandle, struct IStream **a2)
{
  unsigned int v2; // esi
  HANDLE CurrentProcess; // rbx
  HANDLE v6; // rax
  signed int LastError; // eax
  struct IStream *v8; // rcx
  struct IStreamVtbl *v9; // rax
  HANDLE TargetHandle; // [rsp+78h] [rbp+10h] BYREF

  v2 = 0;
  TargetHandle = (HANDLE)-1LL;
  *a2 = 0;
  CurrentProcess = GetCurrentProcess();
  v6 = GetCurrentProcess();
  if ( DuplicateHandle(v6, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    goto LABEL_5;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( !v2 )
  {
LABEL_5:
    v8 = (struct IStream *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = (struct IStreamVtbl *)TargetHandle;
      v8->lpVtbl = (struct IStreamVtbl *)&TFileStream::`vftable';
      v8[1].lpVtbl = v9;
      LODWORD(v8[2].lpVtbl) = 1;
      *a2 = v8;
      return v2;
    }
    *a2 = 0;
    v2 = -2147024882;
  }
  if ( TargetHandle != (HANDLE)-1LL )
    CloseHandle(TargetHandle);
  return v2;
}

```

## disassembly

```asm
0x180005588  push    rbx
0x18000558a  push    rsi
0x18000558b  push    rdi
0x18000558c  push    r14
0x18000558e  sub     rsp, 48h
0x180005592  xor     esi, esi
0x180005594  mov     [rsp+68h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18000559d  mov     [rdx], rsi
0x1800055a0  mov     r14, rdx
0x1800055a3  mov     rdi, rcx
0x1800055a6  call    cs:__imp_GetCurrentProcess
0x1800055ac  mov     rbx, rax
0x1800055af  call    cs:__imp_GetCurrentProcess
0x1800055b5  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800055bd  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x1800055c2  mov     rcx, rax; hSourceProcessHandle
0x1800055c5  mov     [rsp+68h+bInheritHandle], esi; bInheritHandle
0x1800055c9  mov     r8, rbx; hTargetProcessHandle
0x1800055cc  mov     [rsp+68h+dwDesiredAccess], esi; dwDesiredAccess
0x1800055d0  mov     rdx, rdi; hSourceHandle
0x1800055d3  call    cs:__imp_DuplicateHandle
0x1800055d9  test    eax, eax
0x1800055db  jnz     short loc_1800055F6
0x1800055dd  call    cs:__imp_GetLastError
0x1800055e3  mov     esi, eax
0x1800055e5  test    eax, eax
0x1800055e7  jle     short loc_1800055F2
0x1800055e9  movzx   esi, ax
0x1800055ec  or      esi, 80070000h
0x1800055f2  test    esi, esi
0x1800055f4  jnz     short loc_18000563A
0x1800055f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800055fd  mov     ecx, 18h; unsigned __int64
0x180005602  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005607  mov     rcx, rax
0x18000560a  test    rax, rax
0x18000560d  jz      short loc_18000562E
0x18000560f  mov     rax, [rsp+68h+TargetHandle]
0x180005614  lea     rdx, ??_7TFileStream@@6B@; const TFileStream::`vftable'
0x18000561b  mov     [rcx], rdx
0x18000561e  mov     [rcx+8], rax
0x180005622  mov     dword ptr [rcx+10h], 1
0x180005629  mov     [r14], rcx
0x18000562c  jmp     short loc_18000564B
0x18000562e  mov     qword ptr [r14], 0
0x180005635  mov     esi, 8007000Eh
0x18000563a  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18000563f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005643  jz      short loc_18000564B
0x180005645  call    cs:__imp_CloseHandle
0x18000564b  mov     eax, esi
0x18000564d  add     rsp, 48h
0x180005651  pop     r14
0x180005653  pop     rdi
0x180005654  pop     rsi
0x180005655  pop     rbx
0x180005656  retn
```
