# ATL::CDacl::CAccessObjectAce::GetLength(void)

- ea: `0x180047b10`
- end: `0x180047b48`
- name: `?GetLength@CAccessObjectAce@CDacl@ATL@@UEBAIXZ`
- size: `56`
- prototype: `unsigned int __fastcall(ATL::CDacl::CAccessObjectAce *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047b3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047b3a`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessObjectAce::GetLength(ATL::CDacl::CAccessObjectAce *this)
{
  int v1; // ebx

  v1 = *((_QWORD *)this + 19) != 0 ? 28 : 12;
  if ( *((_QWORD *)this + 20) )
    v1 = *((_QWORD *)this + 19) != 0 ? 44 : 28;
  return v1 + GetLengthSid((char *)this + 16);
}

```

## disassembly

```asm
0x180047b10  push    rbx
0x180047b12  sub     rsp, 20h
0x180047b16  mov     rax, [rcx+98h]
0x180047b1d  neg     rax
0x180047b20  sbb     edx, edx
0x180047b22  and     edx, 10h
0x180047b25  add     edx, 1Ch
0x180047b28  cmp     qword ptr [rcx+0A0h], 0
0x180047b30  lea     ebx, [rdx-10h]
0x180047b33  cmovnz  ebx, edx
0x180047b36  add     rcx, 10h; pSid
0x180047b3a  call    cs:__imp_GetLengthSid
0x180047b40  add     eax, ebx
0x180047b42  add     rsp, 20h
0x180047b46  pop     rbx
0x180047b47  retn
```
