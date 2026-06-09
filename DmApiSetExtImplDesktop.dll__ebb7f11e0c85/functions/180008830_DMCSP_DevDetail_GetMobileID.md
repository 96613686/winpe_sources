# DMCSP_DevDetail_GetMobileID

- ea: `0x180008830`
- end: `0x1800088af`
- name: `DMCSP_DevDetail_GetMobileID`
- size: `127`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005384`
- `0x180008830`
- `0x180009efe`
- `0x180009f30`

## import_xrefs

- `DMCmnUtils!GetIMSI` at `0x180008863`
- `DMCmnUtils!GetIMSI` at `0x180008863`

## pseudocode

```c
int __fastcall DMCSP_DevDetail_GetMobileID(unsigned int a1, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  int result; // eax
  unsigned __int16 *v5; // r8
  unsigned __int16 v6[32]; // [rsp+20h] [rbp-58h] BYREF

  v3 = a1;
  memset_0(v6, 0, sizeof(v6));
  result = GetIMSI((unsigned __int16 (*)[32])v6);
  if ( result == -2147020577 )
  {
    v5 = L"Not Present";
  }
  else
  {
    if ( result < 0 )
      return result;
    v5 = v6;
  }
  return StringCchCopyW(a2, v3, v5);
}

```

## disassembly

```asm
0x180008830  mov     [rsp+arg_10], rbx
0x180008835  push    rdi
0x180008836  sub     rsp, 70h
0x18000883a  mov     rax, cs:__security_cookie
0x180008841  xor     rax, rsp
0x180008844  mov     [rsp+78h+var_18], rax
0x180008849  mov     rdi, rdx
0x18000884c  mov     ebx, ecx
0x18000884e  xor     edx, edx; Val
0x180008850  lea     rcx, [rsp+78h+var_58]; void *
0x180008855  lea     r8d, [rdx+40h]; Size
0x180008859  call    memset_0
0x18000885e  lea     rcx, [rsp+78h+var_58]
0x180008863  call    cs:__imp_?GetIMSI@@YAJAEAY0CA@G@Z; GetIMSI(ushort (&)[32])
0x18000886a  nop     dword ptr [rax+rax+00h]
0x18000886f  cmp     eax, 800710DFh
0x180008874  jnz     short loc_18000887F
0x180008876  lea     r8, aNotPresent; "Not Present"
0x18000887d  jmp     short loc_180008888
0x18000887f  test    eax, eax
0x180008881  js      short loc_180008893
0x180008883  lea     r8, [rsp+78h+var_58]; unsigned __int16 *
0x180008888  mov     rdx, rbx; unsigned __int64
0x18000888b  mov     rcx, rdi; unsigned __int16 *
0x18000888e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008893  mov     rcx, [rsp+78h+var_18]
0x180008898  xor     rcx, rsp; StackCookie
0x18000889b  call    __security_check_cookie
0x1800088a0  mov     rbx, [rsp+78h+arg_10]
0x1800088a8  add     rsp, 70h
0x1800088ac  pop     rdi
0x1800088ad  retn
```
