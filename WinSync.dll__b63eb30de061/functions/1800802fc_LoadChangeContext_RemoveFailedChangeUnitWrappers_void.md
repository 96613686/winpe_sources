# LoadChangeContext::RemoveFailedChangeUnitWrappers(void)

- ea: `0x1800802fc`
- end: `0x18008039b`
- name: `?RemoveFailedChangeUnitWrappers@LoadChangeContext@@QEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(LoadChangeContext *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800769b4`
- `0x18007f0e0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18007dbe4`
- `0x1800802fc`

## string_xrefs

- `0x18008032c`: `LoadChangeContext::RemoveFailedChangeUnitWrappers`
- `0x180080372`: `LoadChangeContext::RemoveFailedChangeUnitWrappers`

## pseudocode

```c
__int64 __fastcall LoadChangeContext::RemoveFailedChangeUnitWrappers(LoadChangeContext *this)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_077a61c531f23311e2ad0a8d1ac2f026_Traceguids,
      "LoadChangeContext::RemoveFailedChangeUnitWrappers");
  }
  v2 = ItemChangeWrapper::RemoveChangeUnitChangeWrappers(*((_QWORD *)this + 9), (int *)this + 34);
  v3 = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_077a61c531f23311e2ad0a8d1ac2f026_Traceguids,
      (unsigned int)"LoadChangeContext::RemoveFailedChangeUnitWrappers",
      v2);
  }
  return v3;
}

```

## disassembly

```asm
0x1800802fc  mov     [rsp+arg_0], rbx
0x180080301  push    rdi
0x180080302  sub     rsp, 30h
0x180080306  mov     rbx, rcx
0x180080309  mov     rcx, cs:WPP_GLOBAL_Control
0x180080310  lea     rdi, WPP_GLOBAL_Control
0x180080317  cmp     rcx, rdi
0x18008031a  jz      short loc_180080344
0x18008031c  test    byte ptr [rcx+1Ch], 80h
0x180080320  jz      short loc_180080344
0x180080322  cmp     byte ptr [rcx+19h], 5
0x180080326  jb      short loc_180080344
0x180080328  mov     rcx, [rcx+10h]
0x18008032c  lea     r9, aLoadchangecont_3; "LoadChangeContext::RemoveFailedChangeUn"...
0x180080333  mov     edx, 14h
0x180080338  lea     r8, WPP_077a61c531f23311e2ad0a8d1ac2f026_Traceguids
0x18008033f  call    WPP_SF_s
0x180080344  mov     rcx, [rbx+48h]
0x180080348  lea     rdx, [rbx+88h]
0x18008034f  call    ?RemoveChangeUnitChangeWrappers@ItemChangeWrapper@@QEAAJAEBV?$Vector@VSyncId@@$00@@@Z; ItemChangeWrapper::RemoveChangeUnitChangeWrappers(Vector<SyncId,1> const &)
0x180080354  mov     ebx, eax
0x180080356  mov     rcx, cs:WPP_GLOBAL_Control
0x18008035d  cmp     rcx, rdi
0x180080360  jz      short loc_18008038E
0x180080362  test    byte ptr [rcx+1Ch], 80h
0x180080366  jz      short loc_18008038E
0x180080368  cmp     byte ptr [rcx+19h], 5
0x18008036c  jb      short loc_18008038E
0x18008036e  mov     rcx, [rcx+10h]
0x180080372  lea     r9, aLoadchangecont_3; "LoadChangeContext::RemoveFailedChangeUn"...
0x180080379  mov     edx, 15h
0x18008037e  mov     [rsp+38h+var_18], eax
0x180080382  lea     r8, WPP_077a61c531f23311e2ad0a8d1ac2f026_Traceguids
0x180080389  call    WPP_SF_sD
0x18008038e  mov     eax, ebx
0x180080390  mov     rbx, [rsp+38h+arg_0]
0x180080395  add     rsp, 30h
0x180080399  pop     rdi
0x18008039a  retn
```
