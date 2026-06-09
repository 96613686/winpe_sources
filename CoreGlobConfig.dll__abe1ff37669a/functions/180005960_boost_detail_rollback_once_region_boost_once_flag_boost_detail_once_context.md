# boost::detail::rollback_once_region(boost::once_flag &,boost::detail::once_context &)

- ea: `0x180005960`
- end: `0x1800059d0`
- name: `?rollback_once_region@detail@boost@@YAXAEAUonce_flag@2@AEAUonce_context@12@@Z`
- size: `112`
- prototype: `void __fastcall(boost::detail *__hidden this, struct boost::once_flag *, struct boost::detail::once_context *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180022c50`

## callees

- `0x180005770`
- `0x180005960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800059bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800059bf`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180005996`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180005996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059ad`

## pseudocode

```c
void __fastcall boost::detail::rollback_once_region(
        boost::detail *this,
        struct boost::once_flag *a2,
        struct boost::detail::once_context *a3)
{
  void *v4; // rbx
  HANDLE v5; // rax
  char *v6; // rcx

  _InterlockedExchange((volatile __int32 *)this, 0);
  v4 = (void *)*((_QWORD *)a2 + 2);
  if ( v4 )
    goto LABEL_7;
  if ( !*((_BYTE *)a2 + 24) )
    boost::detail::name_once_mutex((struct boost::once_flag *)((char *)a2 + 24), (char *)this, a3);
  v5 = OpenEventA(0x100002u, 0, (LPCSTR)a2 + 24);
  v6 = (char *)*((_QWORD *)a2 + 2);
  v4 = v5;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *((_QWORD *)a2 + 2) = v4;
  if ( v4 )
LABEL_7:
    SetEvent(v4);
}

```

## disassembly

```asm
0x180005960  mov     [rsp+arg_0], rbx
0x180005965  push    rdi
0x180005966  sub     rsp, 20h
0x18000596a  xor     eax, eax
0x18000596c  mov     rdi, rdx
0x18000596f  xchg    eax, [rcx]
0x180005971  mov     rbx, [rdx+10h]
0x180005975  test    rbx, rbx
0x180005978  jnz     short loc_1800059BC
0x18000597a  cmp     [rdx+18h], bl
0x18000597d  jnz     short loc_18000598B
0x18000597f  mov     rdx, rcx; char *
0x180005982  lea     rcx, [rdi+18h]; this
0x180005986  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x18000598b  lea     r8, [rdi+18h]; lpName
0x18000598f  xor     edx, edx; bInheritHandle
0x180005991  mov     ecx, 100002h; dwDesiredAccess
0x180005996  call    cs:__imp_OpenEventA
0x18000599c  mov     rcx, [rdi+10h]; hObject
0x1800059a0  mov     rbx, rax
0x1800059a3  lea     rax, [rcx-1]
0x1800059a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800059ab  ja      short loc_1800059B3
0x1800059ad  call    cs:__imp_CloseHandle
0x1800059b3  mov     [rdi+10h], rbx
0x1800059b7  test    rbx, rbx
0x1800059ba  jz      short loc_1800059C5
0x1800059bc  mov     rcx, rbx; hEvent
0x1800059bf  call    cs:__imp_SetEvent
0x1800059c5  mov     rbx, [rsp+28h+arg_0]
0x1800059ca  add     rsp, 20h
0x1800059ce  pop     rdi
0x1800059cf  retn
```
