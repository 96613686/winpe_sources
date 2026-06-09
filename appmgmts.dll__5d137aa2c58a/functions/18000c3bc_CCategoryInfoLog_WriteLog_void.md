# CCategoryInfoLog::WriteLog(void)

- ea: `0x18000c3bc`
- end: `0x18000c424`
- name: `?WriteLog@CCategoryInfoLog@@QEAAJXZ`
- size: `104`
- prototype: `int __fastcall(CCategoryInfoLog *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002d40`
- `0x180011fc0`

## callees

- `0x18000c2cc`
- `0x18000c3bc`
- `0x18001bb70`
- `0x18002a3d4`
- `0x18002a754`

## pseudocode

```c
int __fastcall CCategoryInfoLog::WriteLog(CCategoryInfoLog *this)
{
  struct CRsopContext *v1; // rdx
  int result; // eax
  __int64 v4; // rax

  v1 = (struct CRsopContext *)*((_QWORD *)this + 9);
  if ( !*((_DWORD *)v1 + 8) )
    return 0;
  result = CGroupPolicyLog::InitLog(this, v1, L"RSOP_ApplicationManagementCategory");
  if ( result >= 0 )
  {
    result = CGroupPolicyLog::ClearLog(this, 0, 0);
    if ( result >= 0 )
    {
      v4 = *((_QWORD *)this + 9);
      *((_DWORD *)this + 16) = 1;
      if ( *(_DWORD *)(v4 + 36) != 1 )
        return CCategoryInfoLog::WriteCategories(this);
      result = CsGetAppCategories((char *)this + 48);
      if ( result >= 0 )
        return CCategoryInfoLog::WriteCategories(this);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c3bc  push    rbx
0x18000c3be  sub     rsp, 20h
0x18000c3c2  mov     rdx, [rcx+48h]; struct CRsopContext *
0x18000c3c6  mov     rbx, rcx
0x18000c3c9  cmp     dword ptr [rdx+20h], 0
0x18000c3cd  jnz     short loc_18000C3D7
0x18000c3cf  xor     eax, eax
0x18000c3d1  add     rsp, 20h
0x18000c3d5  pop     rbx
0x18000c3d6  retn
0x18000c3d7  lea     r8, aRsopApplicatio_0; "RSOP_ApplicationManagementCategory"
0x18000c3de  call    ?InitLog@CGroupPolicyLog@@QEAAJPEAVCRsopContext@@PEBG@Z; CGroupPolicyLog::InitLog(CRsopContext *,ushort const *)
0x18000c3e3  test    eax, eax
0x18000c3e5  js      short loc_18000C41E
0x18000c3e7  xor     r8d, r8d; int
0x18000c3ea  xor     edx, edx; unsigned __int16 *
0x18000c3ec  mov     rcx, rbx; this
0x18000c3ef  call    ?ClearLog@CGroupPolicyLog@@QEAAJPEBGH@Z; CGroupPolicyLog::ClearLog(ushort const *,int)
0x18000c3f4  test    eax, eax
0x18000c3f6  js      short loc_18000C41E
0x18000c3f8  mov     rax, [rbx+48h]
0x18000c3fc  mov     dword ptr [rbx+40h], 1
0x18000c403  cmp     dword ptr [rax+24h], 1
0x18000c407  jnz     short loc_18000C416
0x18000c409  lea     rcx, [rbx+30h]
0x18000c40d  call    CsGetAppCategories
0x18000c412  test    eax, eax
0x18000c414  js      short loc_18000C41E
0x18000c416  mov     rcx, rbx; this
0x18000c419  call    ?WriteCategories@CCategoryInfoLog@@AEAAJXZ; CCategoryInfoLog::WriteCategories(void)
0x18000c41e  add     rsp, 20h
0x18000c422  pop     rbx
0x18000c423  retn
```
