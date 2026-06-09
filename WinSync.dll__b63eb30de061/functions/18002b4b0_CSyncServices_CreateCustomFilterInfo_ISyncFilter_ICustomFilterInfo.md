# CSyncServices::CreateCustomFilterInfo(ISyncFilter *,ICustomFilterInfo * *)

- ea: `0x18002b4b0`
- end: `0x18002b566`
- name: `?CreateCustomFilterInfo@CSyncServices@@UEAAJPEAUISyncFilter@@PEAPEAUICustomFilterInfo@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct IdParameters **this, struct ISyncFilter *, struct ICustomFilterInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002b4b0`
- `0x18005e148`

## string_xrefs

- `0x18002b4e5`: `CSyncServices::CreateCustomFilterInfo`
- `0x18002b53f`: `CSyncServices::CreateCustomFilterInfo`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateCustomFilterInfo(
        struct IdParameters **this,
        struct ISyncFilter *a2,
        struct ICustomFilterInfo **a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  unsigned int CustomFilterInfo; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateCustomFilterInfo");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[4] )
  {
    CustomFilterInfo = CustomFilterInfo::CreateCustomFilterInfo(this[4], a2, (const struct _GUID *)a3, (void **)a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = CustomFilterInfo;
  }
  else
  {
    v7 = -2147217407;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      65,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateCustomFilterInfo",
      v7);
  return v7;
}

```

## disassembly

```asm
0x18002b4b0  push    rbx
0x18002b4b2  push    rbp
0x18002b4b3  push    rsi
0x18002b4b4  push    rdi
0x18002b4b5  sub     rsp, 38h
0x18002b4b9  mov     rdi, r8
0x18002b4bc  mov     rsi, rdx
0x18002b4bf  mov     rbx, rcx
0x18002b4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4c9  lea     rbp, WPP_GLOBAL_Control
0x18002b4d0  cmp     rcx, rbp
0x18002b4d3  jz      short loc_18002B504
0x18002b4d5  test    byte ptr [rcx+1Ch], 2
0x18002b4d9  jz      short loc_18002B504
0x18002b4db  cmp     byte ptr [rcx+19h], 5
0x18002b4df  jb      short loc_18002B504
0x18002b4e1  mov     rcx, [rcx+10h]
0x18002b4e5  lea     r9, aCsyncservicesC_2; "CSyncServices::CreateCustomFilterInfo"
0x18002b4ec  mov     edx, 40h ; '@'
0x18002b4f1  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b4f8  call    WPP_SF_s
0x18002b4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b504  cmp     qword ptr [rbx+20h], 0
0x18002b509  jnz     short loc_18002B512
0x18002b50b  mov     ebx, 80041001h
0x18002b510  jmp     short loc_18002B52A
0x18002b512  mov     rcx, [rbx+20h]; struct IdParameters *
0x18002b516  mov     r9, rdi; void **
0x18002b519  mov     rdx, rsi; struct ISyncFilter *
0x18002b51c  call    ?CreateCustomFilterInfo@CustomFilterInfo@@SAJPEAVIdParameters@@PEAUISyncFilter@@AEBU_GUID@@PEAPEAX@Z; CustomFilterInfo::CreateCustomFilterInfo(IdParameters *,ISyncFilter *,_GUID const &,void * *)
0x18002b521  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b528  mov     ebx, eax
0x18002b52a  cmp     rcx, rbp
0x18002b52d  jz      short loc_18002B55B
0x18002b52f  test    byte ptr [rcx+1Ch], 2
0x18002b533  jz      short loc_18002B55B
0x18002b535  cmp     byte ptr [rcx+19h], 5
0x18002b539  jb      short loc_18002B55B
0x18002b53b  mov     rcx, [rcx+10h]
0x18002b53f  lea     r9, aCsyncservicesC_2; "CSyncServices::CreateCustomFilterInfo"
0x18002b546  mov     edx, 41h ; 'A'
0x18002b54b  mov     [rsp+58h+var_38], ebx
0x18002b54f  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b556  call    WPP_SF_sD
0x18002b55b  mov     eax, ebx
0x18002b55d  add     rsp, 38h
0x18002b561  pop     rdi
0x18002b562  pop     rsi
0x18002b563  pop     rbp
0x18002b564  pop     rbx
0x18002b565  retn
```
