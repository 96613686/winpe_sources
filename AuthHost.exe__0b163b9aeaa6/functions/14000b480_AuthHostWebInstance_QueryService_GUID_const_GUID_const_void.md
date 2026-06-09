# AuthHostWebInstance::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x14000b480`
- end: `0x14000b50d`
- name: `?QueryService@AuthHostWebInstance@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140002c70`
- `0x14000b480`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::QueryService(
        AuthHostWebInstance *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IAuthenticate.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAuthenticate.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAuthenticate.Data4;
  if ( !v4 )
  {
    v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IAuthenticate.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IAuthenticate.Data1 )
      v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IAuthenticate.Data4;
    if ( !v5 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, const struct _GUID *, _QWORD))(**((_QWORD **)this + 10) + 96LL))(
        *((_QWORD *)this + 10),
        2,
        a3,
        *(_QWORD *)IID_IAuthenticate.Data4);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
      }
    }
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x14000b480  sub     rsp, 28h
0x14000b484  mov     rax, [rdx]
0x14000b487  mov     r10, qword ptr cs:IID_IAuthenticate.Data1
0x14000b48e  mov     r9, qword ptr cs:IID_IAuthenticate.Data4
0x14000b495  sub     rax, r10
0x14000b498  jnz     short loc_14000B4A1
0x14000b49a  mov     rax, [rdx+8]
0x14000b49e  sub     rax, r9
0x14000b4a1  test    rax, rax
0x14000b4a4  jnz     short loc_14000B503
0x14000b4a6  mov     rax, [r8]
0x14000b4a9  sub     rax, r10
0x14000b4ac  jnz     short loc_14000B4B5
0x14000b4ae  mov     rax, [r8+8]
0x14000b4b2  sub     rax, r9
0x14000b4b5  test    rax, rax
0x14000b4b8  jnz     short loc_14000B503
0x14000b4ba  mov     rcx, [rcx+50h]
0x14000b4be  mov     edx, 2
0x14000b4c3  mov     rax, [rcx]
0x14000b4c6  mov     rax, [rax+60h]
0x14000b4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b4cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4d6  lea     rax, WPP_GLOBAL_Control
0x14000b4dd  cmp     rcx, rax
0x14000b4e0  jz      short loc_14000B503
0x14000b4e2  test    byte ptr [rcx+44h], 4
0x14000b4e6  jz      short loc_14000B503
0x14000b4e8  cmp     byte ptr [rcx+41h], 5
0x14000b4ec  jb      short loc_14000B503
0x14000b4ee  mov     rcx, [rcx+38h]
0x14000b4f2  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b4f9  mov     edx, 36h ; '6'
0x14000b4fe  call    WPP_SF_
0x14000b503  mov     eax, 80004002h
0x14000b508  add     rsp, 28h
0x14000b50c  retn
```
