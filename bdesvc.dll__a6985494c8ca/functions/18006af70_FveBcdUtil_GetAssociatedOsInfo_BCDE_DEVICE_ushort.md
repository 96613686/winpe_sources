# FveBcdUtil::GetAssociatedOsInfo(_BCDE_DEVICE * *,ushort * *)

- ea: `0x18006af70`
- end: `0x18006b0b1`
- name: `?GetAssociatedOsInfo@FveBcdUtil@@SAJPEAPEAU_BCDE_DEVICE@@PEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct _BCDE_DEVICE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18006a51c`

## callees

- `0x18001b890`
- `0x180034070`
- `0x180034610`
- `0x18006ad70`
- `0x18006af70`
- `0x18006b0b8`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x18006afba`
- `bcd!BcdOpenSystemStore` at `0x18006afba`
- `bcd!BcdOpenObject` at `0x18006afff`
- `bcd!BcdOpenObject` at `0x18006afff`
- `bcd!BcdCloseStore` at `0x18006b087`
- `bcd!BcdCloseStore` at `0x18007d2a5`
- `bcd!BcdCloseStore` at `0x18006b087`
- `bcd!BcdCloseStore` at `0x18007d2a5`
- `bcd!BcdCloseObject` at `0x18006b076`
- `bcd!BcdCloseObject` at `0x18007d295`
- `bcd!BcdCloseObject` at `0x18006b076`
- `bcd!BcdCloseObject` at `0x18007d295`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOsInfo(struct _BCDE_DEVICE **a1, unsigned __int16 **a2)
{
  int v3; // eax
  int AssociatedOs; // ebx
  int v5; // eax
  void *v6; // rcx
  void *v8; // [rsp+28h] [rbp-50h] BYREF
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  void *v10; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-30h]
  struct _GUID v13; // [rsp+50h] [rbp-28h] BYREF

  v13 = 0;
  v8 = 0;
  v10 = 0;
  Block = 0;
  v12 = 0;
  v3 = BcdOpenSystemStore(&v8);
  AssociatedOs = FromNtStatus(v3);
  if ( AssociatedOs >= 0 )
  {
    AssociatedOs = FveBcdUtil::GetAssociatedOs(v8, &v13);
    if ( AssociatedOs >= 0 )
    {
      v5 = BcdOpenObject(v8, &v13, &v10);
      AssociatedOs = FromNtStatus(v5);
      if ( AssociatedOs >= 0 )
      {
        AssociatedOs = FveBcdUtil::GetBcdElementData(v10, 0x11000001u, &Block, &v11);
        if ( AssociatedOs >= 0 )
        {
          *a1 = (struct _BCDE_DEVICE *)Block;
          Block = 0;
        }
      }
    }
  }
  if ( Block )
    operator delete(Block);
  v6 = v8;
  if ( v8 )
  {
    if ( v10 )
    {
      BcdCloseObject(v10);
      v6 = v8;
    }
    BcdCloseStore(v6);
  }
  return (unsigned int)AssociatedOs;
}

```

## disassembly

```asm
0x18006af70  mov     r11, rsp
0x18006af73  mov     [r11+10h], rbx
0x18006af77  push    rdi
0x18006af78  sub     rsp, 70h
0x18006af7c  mov     rax, cs:__security_cookie
0x18006af83  xor     rax, rsp
0x18006af86  mov     [rsp+78h+var_18], rax
0x18006af8b  mov     rdi, rcx
0x18006af8e  xorps   xmm0, xmm0
0x18006af91  movups  xmmword ptr [rsp+78h+var_28.Data1], xmm0
0x18006af96  mov     qword ptr [r11-50h], 0
0x18006af9e  mov     qword ptr [r11-40h], 0
0x18006afa6  mov     qword ptr [r11-48h], 0
0x18006afae  mov     qword ptr [r11-30h], 0
0x18006afb6  lea     rcx, [r11-50h]
0x18006afba  call    cs:__imp_BcdOpenSystemStore
0x18006afc1  nop     dword ptr [rax+rax+00h]
0x18006afc6  mov     ecx, eax; int
0x18006afc8  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006afcd  mov     ebx, eax
0x18006afcf  mov     [rsp+78h+var_58], eax
0x18006afd3  test    eax, eax
0x18006afd5  js      short loc_18006B050
0x18006afd7  lea     rdx, [rsp+78h+var_28]; struct _GUID *
0x18006afdc  mov     rcx, [rsp+78h+var_50]; void *
0x18006afe1  call    ?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetAssociatedOs(void *,_GUID *)
0x18006afe6  mov     ebx, eax
0x18006afe8  mov     [rsp+78h+var_58], eax
0x18006afec  test    eax, eax
0x18006afee  js      short loc_18006B050
0x18006aff0  lea     r8, [rsp+78h+var_40]
0x18006aff5  lea     rdx, [rsp+78h+var_28]
0x18006affa  mov     rcx, [rsp+78h+var_50]
0x18006afff  call    cs:__imp_BcdOpenObject
0x18006b006  nop     dword ptr [rax+rax+00h]
0x18006b00b  mov     ecx, eax; int
0x18006b00d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006b012  mov     ebx, eax
0x18006b014  mov     [rsp+78h+var_58], eax
0x18006b018  test    eax, eax
0x18006b01a  js      short loc_18006B050
0x18006b01c  lea     r9, [rsp+78h+var_38]; unsigned int *
0x18006b021  lea     r8, [rsp+78h+Block]; void **
0x18006b026  mov     edx, 11000001h; unsigned int
0x18006b02b  mov     rcx, [rsp+78h+var_40]; void *
0x18006b030  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18006b035  mov     ebx, eax
0x18006b037  mov     [rsp+78h+var_58], eax
0x18006b03b  test    eax, eax
0x18006b03d  js      short loc_18006B050
0x18006b03f  mov     rax, [rsp+78h+Block]
0x18006b044  mov     [rdi], rax
0x18006b047  mov     [rsp+78h+Block], 0
0x18006b050  mov     rcx, [rsp+78h+Block]; Block
0x18006b055  test    rcx, rcx
0x18006b058  jz      short loc_18006B05F
0x18006b05a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006b05f  mov     rcx, [rsp+78h+var_50]
0x18006b064  test    rcx, rcx
0x18006b067  jz      short loc_18006B093
0x18006b069  mov     rax, [rsp+78h+var_40]
0x18006b06e  test    rax, rax
0x18006b071  jz      short loc_18006B087
0x18006b073  mov     rcx, rax
0x18006b076  call    cs:__imp_BcdCloseObject
0x18006b07d  nop     dword ptr [rax+rax+00h]
0x18006b082  mov     rcx, [rsp+78h+var_50]
0x18006b087  call    cs:__imp_BcdCloseStore
0x18006b08e  nop     dword ptr [rax+rax+00h]
0x18006b093  mov     eax, ebx
0x18006b095  mov     rcx, [rsp+78h+var_18]
0x18006b09a  xor     rcx, rsp; StackCookie
0x18006b09d  call    __security_check_cookie
0x18006b0a2  mov     rbx, [rsp+78h+arg_8]
0x18006b0aa  add     rsp, 70h
0x18006b0ae  pop     rdi
0x18006b0af  retn
0x18007d259  push    rbp
0x18007d25b  sub     rsp, 20h
0x18007d25f  mov     rbp, rdx
0x18007d262  mov     rcx, [rbp+30h]; Block
0x18007d266  test    rcx, rcx
0x18007d269  jz      short loc_18007D271
0x18007d26b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d270  nop
0x18007d271  mov     rcx, [rbp+48h]; Block
0x18007d275  test    rcx, rcx
0x18007d278  jz      short loc_18007D280
0x18007d27a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d27f  nop
0x18007d280  mov     rcx, [rbp+28h]
0x18007d284  test    rcx, rcx
0x18007d287  jz      short loc_18007D2B2
0x18007d289  mov     rax, [rbp+38h]
0x18007d28d  test    rax, rax
0x18007d290  jz      short loc_18007D2A5
0x18007d292  mov     rcx, rax
0x18007d295  call    cs:__imp_BcdCloseObject
0x18007d29c  nop     dword ptr [rax+rax+00h]
0x18007d2a1  mov     rcx, [rbp+28h]
0x18007d2a5  call    cs:__imp_BcdCloseStore
0x18007d2ac  nop     dword ptr [rax+rax+00h]
0x18007d2b1  nop
0x18007d2b2  add     rsp, 20h
0x18007d2b6  pop     rbp
0x18007d2b7  retn
```
