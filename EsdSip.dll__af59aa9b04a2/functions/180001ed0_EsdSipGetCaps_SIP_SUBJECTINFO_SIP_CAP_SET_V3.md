# EsdSipGetCaps(SIP_SUBJECTINFO_ *,_SIP_CAP_SET_V3 *)

- ea: `0x180001ed0`
- end: `0x180001f02`
- name: `?EsdSipGetCaps@@YAHPEAUSIP_SUBJECTINFO_@@PEAU_SIP_CAP_SET_V3@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, struct _SIP_CAP_SET_V3 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001ed0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001ef5`
- `KERNEL32!SetLastError` at `0x180001ef5`

## pseudocode

```c
__int64 __fastcall EsdSipGetCaps(struct SIP_SUBJECTINFO_ *a1, struct _SIP_CAP_SET_V3 *a2)
{
  __int64 result; // rax

  if ( a2 && *(_DWORD *)a2 >= 0x10u )
  {
    result = 1;
    *((_DWORD *)a2 + 1) = 0x10000;
    *((_QWORD *)a2 + 1) = 1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001ed0  sub     rsp, 28h
0x180001ed4  test    rdx, rdx
0x180001ed7  jz      short loc_180001EF0
0x180001ed9  cmp     dword ptr [rdx], 10h
0x180001edc  jb      short loc_180001EF0
0x180001ede  mov     eax, 1
0x180001ee3  mov     dword ptr [rdx+4], 10000h
0x180001eea  mov     [rdx+8], rax
0x180001eee  jmp     short loc_180001EFD
0x180001ef0  mov     ecx, 57h ; 'W'; dwErrCode
0x180001ef5  call    cs:__imp_SetLastError
0x180001efb  xor     eax, eax
0x180001efd  add     rsp, 28h
0x180001f01  retn
```
