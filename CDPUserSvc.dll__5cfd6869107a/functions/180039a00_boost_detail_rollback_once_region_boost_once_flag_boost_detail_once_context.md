# boost::detail::rollback_once_region(boost::once_flag &,boost::detail::once_context &)

- ea: `0x180039a00`
- end: `0x180039a70`
- name: `?rollback_once_region@detail@boost@@YAXAEAUonce_flag@2@AEAUonce_context@12@@Z`
- size: `112`
- prototype: `void __fastcall(boost::detail *__hidden this, struct boost::once_flag *, struct boost::detail::once_context *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180060170`

## callees

- `0x180039810`
- `0x180039a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039a5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039a5f`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180039a36`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x180039a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a4d`

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
0x180039a00  mov     [rsp+arg_0], rbx
0x180039a05  push    rdi
0x180039a06  sub     rsp, 20h
0x180039a0a  xor     eax, eax
0x180039a0c  mov     rdi, rdx
0x180039a0f  xchg    eax, [rcx]
0x180039a11  mov     rbx, [rdx+10h]
0x180039a15  test    rbx, rbx
0x180039a18  jnz     short loc_180039A5C
0x180039a1a  cmp     [rdx+18h], bl
0x180039a1d  jnz     short loc_180039A2B
0x180039a1f  mov     rdx, rcx; char *
0x180039a22  lea     rcx, [rdi+18h]; this
0x180039a26  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x180039a2b  lea     r8, [rdi+18h]; lpName
0x180039a2f  xor     edx, edx; bInheritHandle
0x180039a31  mov     ecx, 100002h; dwDesiredAccess
0x180039a36  call    cs:__imp_OpenEventA
0x180039a3c  mov     rcx, [rdi+10h]; hObject
0x180039a40  mov     rbx, rax
0x180039a43  lea     rax, [rcx-1]
0x180039a47  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039a4b  ja      short loc_180039A53
0x180039a4d  call    cs:__imp_CloseHandle
0x180039a53  mov     [rdi+10h], rbx
0x180039a57  test    rbx, rbx
0x180039a5a  jz      short loc_180039A65
0x180039a5c  mov     rcx, rbx; hEvent
0x180039a5f  call    cs:__imp_SetEvent
0x180039a65  mov     rbx, [rsp+28h+arg_0]
0x180039a6a  add     rsp, 20h
0x180039a6e  pop     rdi
0x180039a6f  retn
```
