# ATL::CSecurityDescriptor::CloneSID(void * *,void *)

- ea: `0x140012ac4`
- end: `0x140012b58`
- name: `?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z`
- size: `148`
- prototype: `static int(void **, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001de48`
- `0x1400287f4`
- `0x14002896c`

## callees

- `0x1400124cc`
- `0x140012ac4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140012b39`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140012b39`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140012b06`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140012b06`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140012b25`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140012b25`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140012afc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140012afc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140012aef`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140012aef`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::CloneSID(void **a1, void *a2)
{
  DWORD LengthSid; // ebp
  void *v6; // rax
  unsigned int Error; // esi

  if ( !a1 )
    return 2147500035LL;
  if ( *a1 )
    return 2147942487LL;
  *a1 = 0;
  if ( !IsValidSid(a2) )
    return 2147942487LL;
  LengthSid = GetLengthSid(a2);
  v6 = malloc(LengthSid);
  *a1 = v6;
  if ( !v6 )
    return 2147942414LL;
  Error = 0;
  if ( !CopySid(LengthSid, v6, a2) )
  {
    Error = ResultFromLastError();
    free(*a1);
    *a1 = 0;
  }
  return Error;
}

```

## disassembly

```asm
0x140012ac4  push    rbx
0x140012ac6  push    rbp
0x140012ac7  push    rsi
0x140012ac8  push    rdi
0x140012ac9  sub     rsp, 28h
0x140012acd  mov     rdi, rdx
0x140012ad0  mov     rbx, rcx
0x140012ad3  test    rcx, rcx
0x140012ad6  jnz     short loc_140012ADF
0x140012ad8  mov     eax, 80004003h
0x140012add  jmp     short loc_140012B4F
0x140012adf  cmp     qword ptr [rcx], 0
0x140012ae3  jnz     short loc_140012B4A
0x140012ae5  mov     qword ptr [rcx], 0
0x140012aec  mov     rcx, rdi; pSid
0x140012aef  call    cs:__imp_IsValidSid
0x140012af5  test    eax, eax
0x140012af7  jz      short loc_140012B4A
0x140012af9  mov     rcx, rdi; pSid
0x140012afc  call    cs:__imp_GetLengthSid
0x140012b02  mov     ecx, eax; Size
0x140012b04  mov     ebp, eax
0x140012b06  call    cs:__imp_malloc
0x140012b0c  mov     [rbx], rax
0x140012b0f  test    rax, rax
0x140012b12  jnz     short loc_140012B1B
0x140012b14  mov     eax, 8007000Eh
0x140012b19  jmp     short loc_140012B4F
0x140012b1b  mov     r8, rdi; pSourceSid
0x140012b1e  mov     rdx, rax; pDestinationSid
0x140012b21  mov     ecx, ebp; nDestinationSidLength
0x140012b23  xor     esi, esi
0x140012b25  call    cs:__imp_CopySid
0x140012b2b  test    eax, eax
0x140012b2d  jnz     short loc_140012B46
0x140012b2f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140012b34  mov     rcx, [rbx]; Block
0x140012b37  mov     esi, eax
0x140012b39  call    cs:__imp_free
0x140012b3f  mov     qword ptr [rbx], 0
0x140012b46  mov     eax, esi
0x140012b48  jmp     short loc_140012B4F
0x140012b4a  mov     eax, 80070057h
0x140012b4f  add     rsp, 28h
0x140012b53  pop     rdi
0x140012b54  pop     rsi
0x140012b55  pop     rbp
0x140012b56  pop     rbx
0x140012b57  retn
```
