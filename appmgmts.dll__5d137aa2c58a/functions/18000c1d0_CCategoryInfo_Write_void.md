# CCategoryInfo::Write(void)

- ea: `0x18000c1d0`
- end: `0x18000c2c3`
- name: `?Write@CCategoryInfo@@UEAAJXZ`
- size: `243`
- prototype: `int __fastcall(CCategoryInfo *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800016d0`
- `0x18000c1d0`
- `0x180012fbc`
- `0x18001b1a0`
- `0x180029eb4`
- `0x18002a2b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000c229`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000c229`

## pseudocode

```c
int __fastcall CCategoryInfo::Write(CCategoryInfo *this)
{
  int result; // eax
  int v3; // eax
  int v4; // eax
  int v5; // ebx
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int16 v7[40]; // [rsp+30h] [rbp-68h] BYREF

  GuidToString((struct _GUID *)(*((_QWORD *)this + 3) + 16LL), v7);
  result = CGroupPolicyRecord::SetValue(this, L"CategoryId", v7);
  if ( result >= 0 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v3 = CGroupPolicyRecord::SetValue(this, L"CreationTime", &SystemTime);
    if ( v3 < 0 && *(_DWORD *)&gDebugLevel )
      _DebugMsg(4, 0xC29u, L"CreationTime", (unsigned int)v3);
    v4 = CGroupPolicyRecord::SetValue(this, L"Name", *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 8LL));
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC29u, L"Name", (unsigned int)v4);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000c1d0  push    rbx
0x18000c1d2  sub     rsp, 90h
0x18000c1d9  mov     rax, cs:__security_cookie
0x18000c1e0  xor     rax, rsp
0x18000c1e3  mov     [rsp+98h+var_18], rax
0x18000c1eb  mov     rbx, rcx
0x18000c1ee  lea     rdx, [rsp+98h+var_68]; unsigned __int16 *
0x18000c1f3  mov     rcx, [rcx+18h]
0x18000c1f7  add     rcx, 10h; struct _GUID *
0x18000c1fb  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000c200  lea     r8, [rsp+98h+var_68]; unsigned __int16 *
0x18000c205  mov     rcx, rbx; this
0x18000c208  lea     rdx, aCategoryid; "CategoryId"
0x18000c20f  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x18000c214  test    eax, eax
0x18000c216  js      loc_18000C2AA
0x18000c21c  xorps   xmm0, xmm0
0x18000c21f  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x18000c224  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x18000c229  call    cs:__imp_GetSystemTime
0x18000c22f  lea     r8, [rsp+98h+SystemTime]; struct _SYSTEMTIME *
0x18000c234  mov     rcx, rbx; this
0x18000c237  lea     rdx, aCreationtime; "CreationTime"
0x18000c23e  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGPEAU_SYSTEMTIME@@@Z; CGroupPolicyRecord::SetValue(ushort const *,_SYSTEMTIME *)
0x18000c243  test    eax, eax
0x18000c245  jns     short loc_18000C269
0x18000c247  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c24e  jz      short loc_18000C269
0x18000c250  mov     r9d, eax
0x18000c253  lea     r8, aCreationtime; "CreationTime"
0x18000c25a  mov     edx, 0C29h; unsigned int
0x18000c25f  mov     ecx, 4; unsigned int
0x18000c264  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c269  mov     r8, [rbx+18h]
0x18000c26d  lea     rdx, aName; "Name"
0x18000c274  mov     rcx, rbx; this
0x18000c277  mov     r8, [r8+8]; unsigned __int16 *
0x18000c27b  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x18000c280  mov     ebx, eax
0x18000c282  test    eax, eax
0x18000c284  jns     short loc_18000C2A8
0x18000c286  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c28d  jz      short loc_18000C2A8
0x18000c28f  mov     r9d, eax
0x18000c292  lea     r8, aName; "Name"
0x18000c299  mov     edx, 0C29h; unsigned int
0x18000c29e  mov     ecx, 4; unsigned int
0x18000c2a3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c2a8  mov     eax, ebx
0x18000c2aa  mov     rcx, [rsp+98h+var_18]
0x18000c2b2  xor     rcx, rsp; StackCookie
0x18000c2b5  call    __security_check_cookie
0x18000c2ba  add     rsp, 90h
0x18000c2c1  pop     rbx
0x18000c2c2  retn
```
