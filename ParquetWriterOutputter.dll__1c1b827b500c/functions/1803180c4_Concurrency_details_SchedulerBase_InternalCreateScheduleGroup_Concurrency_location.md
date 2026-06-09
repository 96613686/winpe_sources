# Concurrency::details::SchedulerBase::InternalCreateScheduleGroup(Concurrency::location *)

- ea: `0x1803180c4`
- end: `0x1803181d2`
- name: `?InternalCreateScheduleGroup@SchedulerBase@details@Concurrency@@AEAAPEAVScheduleGroup@3@PEAVlocation@3@@Z`
- size: `270`
- prototype: `struct Concurrency::ScheduleGroup *__fastcall(Concurrency::details::SchedulerBase *__hidden this, struct Concurrency::location *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180316810`
- `0x180316820`

## callees

- `0x1802f0fb0`
- `0x180315bcc`
- `0x1803180c4`
- `0x1803243dc`
- `0x1803253f0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1803180f0`
- `KERNEL32!InterlockedPopEntrySList` at `0x1803180f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Concurrency::ScheduleGroup *__fastcall Concurrency::details::SchedulerBase::InternalCreateScheduleGroup(
        union _SLIST_HEADER *this,
        struct Concurrency::location *a2)
{
  union _SLIST_HEADER *v4; // rbp
  PSLIST_ENTRY v5; // rax
  Concurrency::details::ScheduleGroupBase *v6; // rbx
  Concurrency::details::ScheduleGroupBase *v7; // rax
  struct Concurrency::location *v8; // rdx
  Concurrency::details::ScheduleGroupBase *v9; // rax
  _DWORD v11[2]; // [rsp+28h] [rbp-20h] BYREF
  __int128 v12; // [rsp+30h] [rbp-18h]

  v4 = this + 11;
  v5 = InterlockedPopEntrySList(this + 11);
  if ( v5 )
    v6 = (Concurrency::details::ScheduleGroupBase *)&v5[-6];
  else
    v6 = 0;
  if ( !*((_DWORD *)&this[1].HeaderX64 + 1) )
  {
    if ( !v6 )
    {
      v7 = (Concurrency::details::ScheduleGroupBase *)operator new(0x70u);
      v6 = v7;
      if ( v7 )
      {
        Concurrency::details::ScheduleGroupBase::ScheduleGroupBase(
          v7,
          (struct Concurrency::details::SchedulerBase *)this,
          a2);
        *(_QWORD *)v6 = &Concurrency::details::CacheLocalScheduleGroup::`vftable';
        *((_BYTE *)v6 + 80) = 1;
      }
      else
      {
        v6 = 0;
      }
      goto LABEL_16;
    }
    v8 = a2;
LABEL_15:
    Concurrency::details::ScheduleGroupBase::Initialize(v6, v8);
    goto LABEL_16;
  }
  v11[0] = 0;
  v11[1] = 0;
  v12 = 0;
  if ( v6 )
  {
    v8 = (struct Concurrency::location *)v11;
    goto LABEL_15;
  }
  v9 = (Concurrency::details::ScheduleGroupBase *)operator new(0x80u);
  v6 = v9;
  if ( v9 )
  {
    Concurrency::details::ScheduleGroupBase::ScheduleGroupBase(
      v9,
      (struct Concurrency::details::SchedulerBase *)this,
      (struct Concurrency::location *)v11);
    *(_QWORD *)v6 = &Concurrency::details::FairScheduleGroup::`vftable';
    *((_QWORD *)v6 + 14) = 0;
    *((_BYTE *)v6 + 80) = 2;
  }
  else
  {
    v6 = 0;
  }
LABEL_16:
  Concurrency::details::ListArray<Concurrency::details::ScheduleGroupBase>::Add(v4, v6);
  return v6;
}

```

## disassembly

```asm
0x1803180c4  mov     rax, rsp
0x1803180c7  push    rdi
0x1803180c8  sub     rsp, 40h
0x1803180cc  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1803180d4  mov     [rax+10h], rbx
0x1803180d8  mov     [rax+18h], rbp
0x1803180dc  mov     [rax+20h], rsi
0x1803180e0  mov     rsi, rdx
0x1803180e3  mov     rdi, rcx
0x1803180e6  lea     rbp, [rcx+0B0h]
0x1803180ed  mov     rcx, rbp; ListHead
0x1803180f0  call    cs:__imp_InterlockedPopEntrySList
0x1803180f6  test    rax, rax
0x1803180f9  jnz     short loc_1803180FF
0x1803180fb  xor     ebx, ebx
0x1803180fd  jmp     short loc_180318103
0x1803180ff  lea     rbx, [rax-60h]
0x180318103  cmp     dword ptr [rdi+14h], 0
0x180318107  jnz     short loc_18031814A
0x180318109  test    rbx, rbx
0x18031810c  jnz     short loc_180318145
0x18031810e  lea     ecx, [rbx+70h]; Size
0x180318111  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180318116  mov     rbx, rax
0x180318119  mov     [rsp+48h+arg_0], rax
0x18031811e  test    rax, rax
0x180318121  jz      short loc_180318141
0x180318123  mov     r8, rsi; struct Concurrency::location *
0x180318126  mov     rdx, rdi; struct Concurrency::details::SchedulerBase *
0x180318129  mov     rcx, rax; this
0x18031812c  call    ??0ScheduleGroupBase@details@Concurrency@@QEAA@PEAVSchedulerBase@12@PEAVlocation@2@@Z; Concurrency::details::ScheduleGroupBase::ScheduleGroupBase(Concurrency::details::SchedulerBase *,Concurrency::location *)
0x180318131  lea     rax, ??_7CacheLocalScheduleGroup@details@Concurrency@@6B@; const Concurrency::details::CacheLocalScheduleGroup::`vftable'
0x180318138  mov     [rbx], rax
0x18031813b  mov     byte ptr [rbx+50h], 1
0x18031813f  jmp     short loc_180318143
0x180318141  xor     ebx, ebx
0x180318143  jmp     short loc_1803181AF
0x180318145  mov     rdx, rsi
0x180318148  jmp     short loc_1803181A7
0x18031814a  and     [rsp+48h+var_20], 0
0x18031814f  and     [rsp+48h+var_1C], 0
0x180318154  xorps   xmm0, xmm0
0x180318157  movdqu  [rsp+48h+var_18], xmm0
0x18031815d  test    rbx, rbx
0x180318160  jnz     short loc_1803181A2
0x180318162  mov     ecx, 80h; Size
0x180318167  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18031816c  mov     rbx, rax
0x18031816f  mov     [rsp+48h+arg_0], rax
0x180318174  test    rax, rax
0x180318177  jz      short loc_18031819E
0x180318179  lea     r8, [rsp+48h+var_20]; struct Concurrency::location *
0x18031817e  mov     rdx, rdi; struct Concurrency::details::SchedulerBase *
0x180318181  mov     rcx, rax; this
0x180318184  call    ??0ScheduleGroupBase@details@Concurrency@@QEAA@PEAVSchedulerBase@12@PEAVlocation@2@@Z; Concurrency::details::ScheduleGroupBase::ScheduleGroupBase(Concurrency::details::SchedulerBase *,Concurrency::location *)
0x180318189  lea     rax, ??_7FairScheduleGroup@details@Concurrency@@6B@; const Concurrency::details::FairScheduleGroup::`vftable'
0x180318190  mov     [rbx], rax
0x180318193  and     qword ptr [rbx+70h], 0
0x180318198  mov     byte ptr [rbx+50h], 2
0x18031819c  jmp     short loc_1803181A0
0x18031819e  xor     ebx, ebx
0x1803181a0  jmp     short loc_1803181AF
0x1803181a2  lea     rdx, [rsp+48h+var_20]; struct Concurrency::location *
0x1803181a7  mov     rcx, rbx; this
0x1803181aa  call    ?Initialize@ScheduleGroupBase@details@Concurrency@@QEAAXPEAVlocation@3@@Z; Concurrency::details::ScheduleGroupBase::Initialize(Concurrency::location *)
0x1803181af  mov     rdx, rbx
0x1803181b2  mov     rcx, rbp
0x1803181b5  call    ?Add@?$ListArray@VScheduleGroupBase@details@Concurrency@@@details@Concurrency@@QEAAHPEAVScheduleGroupBase@23@@Z; Concurrency::details::ListArray<Concurrency::details::ScheduleGroupBase>::Add(Concurrency::details::ScheduleGroupBase *)
0x1803181ba  mov     rax, rbx
0x1803181bd  mov     rbx, [rsp+48h+arg_8]
0x1803181c2  mov     rbp, [rsp+48h+arg_10]
0x1803181c7  mov     rsi, [rsp+48h+arg_18]
0x1803181cc  add     rsp, 40h
0x1803181d0  pop     rdi
0x1803181d1  retn
```
