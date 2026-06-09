# UnsubscribeActivityCoordinatorPolicyInternal

- ea: `0x18001ab44`
- end: `0x18001ab95`
- name: `UnsubscribeActivityCoordinatorPolicyInternal`
- size: `81`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a820`
- `0x18001aa04`

## callees

- `0x180004550`
- `0x180004570`
- `0x18001a964`
- `0x18001ab44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ab54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ab54`

## pseudocode

```c
__int64 __fastcall UnsubscribeActivityCoordinatorPolicyInternal(_DWORD *a1)
{
  int v1; // ebx

  v1 = a1[8];
  if ( v1 == GetCurrentThreadId() )
    __fastfail(0x38u);
  if ( *((_QWORD *)a1 + 1) )
    CrmActivityFree();
  if ( *(_QWORD *)a1 )
    AcpReleaseClientRegistration();
  HamFreeBuffer(a1);
  return 0;
}

```

## disassembly

```asm
0x18001ab44  mov     [rsp+arg_0], rbx
0x18001ab49  push    rdi
0x18001ab4a  sub     rsp, 20h
0x18001ab4e  mov     ebx, [rcx+20h]
0x18001ab51  mov     rdi, rcx
0x18001ab54  call    cs:__imp_GetCurrentThreadId
0x18001ab5a  cmp     ebx, eax
0x18001ab5c  jnz     short loc_18001AB65
0x18001ab5e  mov     ecx, 38h ; '8'
0x18001ab63  int     29h; Win8: RtlFailFast(ecx)
0x18001ab65  mov     rcx, [rdi+8]
0x18001ab69  test    rcx, rcx
0x18001ab6c  jz      short loc_18001AB73
0x18001ab6e  call    CrmActivityFree
0x18001ab73  mov     rcx, [rdi]
0x18001ab76  test    rcx, rcx
0x18001ab79  jz      short loc_18001AB80
0x18001ab7b  call    AcpReleaseClientRegistration
0x18001ab80  mov     rcx, rdi
0x18001ab83  call    HamFreeBuffer
0x18001ab88  mov     rbx, [rsp+28h+arg_0]
0x18001ab8d  xor     eax, eax
0x18001ab8f  add     rsp, 20h
0x18001ab93  pop     rdi
0x18001ab94  retn
```
