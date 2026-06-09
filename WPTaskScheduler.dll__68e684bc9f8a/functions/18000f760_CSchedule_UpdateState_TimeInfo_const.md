# CSchedule::UpdateState(TimeInfo const &)

- ea: `0x18000f760`
- end: `0x18000f7c3`
- name: `?UpdateState@CSchedule@@AEAAXAEBVTimeInfo@@@Z`
- size: `99`
- prototype: `void __fastcall(CSchedule *__hidden this, const struct TimeInfo *)`
- caller_count: `11`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800025b0`
- `0x180005e40`
- `0x1800074e0`
- `0x18000f570`
- `0x18000f634`
- `0x180017a74`
- `0x180017c04`
- `0x180017e48`
- `0x180018158`
- `0x180018208`
- `0x180018314`

## callees

- `0x18000d290`
- `0x18000d460`
- `0x18000f760`
- `0x180018128`

## pseudocode

```c
void __fastcall CSchedule::UpdateState(CSchedule *this, const struct TimeInfo *a2)
{
  CSchedule *v3; // rcx
  BOOL v4; // edx
  _BYTE v5[56]; // [rsp+20h] [rbp-38h] BYREF

  CSchedule::GetTimeInFormat((__int64)this, (__int64)v5, (__int64)a2);
  if ( *((_DWORD *)v3 + 36) >= *((_DWORD *)v3 + 37) || *((_DWORD *)v3 + 10) == 5 )
  {
    v4 = 1;
  }
  else if ( (unsigned int)CSchedule::IsPastDue(v3, (const struct TimeValue *)v5) )
  {
    v4 = CSchedule::IsWithinInterval(this, (const struct TimeValue *)v5) == 0;
  }
  else
  {
    v4 = 0;
  }
  *((_DWORD *)this + 66) = v4;
}

```

## disassembly

```asm
0x18000f760  push    rbx
0x18000f762  sub     rsp, 50h
0x18000f766  mov     r8, rdx
0x18000f769  mov     rbx, rcx
0x18000f76c  lea     rdx, [rsp+58h+var_38]
0x18000f771  call    ?GetTimeInFormat@CSchedule@@AEAA?AVTimeValue@@AEBVTimeInfo@@@Z; CSchedule::GetTimeInFormat(TimeInfo const &)
0x18000f776  mov     edx, [rcx+94h]
0x18000f77c  cmp     [rcx+90h], edx
0x18000f782  jnb     short loc_18000F78A
0x18000f784  cmp     dword ptr [rcx+28h], 5
0x18000f788  jnz     short loc_18000F791
0x18000f78a  mov     edx, 1
0x18000f78f  jmp     short loc_18000F7B7
0x18000f791  lea     rdx, [rsp+58h+var_38]; struct TimeValue *
0x18000f796  call    ?IsPastDue@CSchedule@@AEAAHAEBVTimeValue@@@Z; CSchedule::IsPastDue(TimeValue const &)
0x18000f79b  test    eax, eax
0x18000f79d  jz      short loc_18000F7B5
0x18000f79f  lea     rdx, [rsp+58h+var_38]; struct TimeValue *
0x18000f7a4  mov     rcx, rbx; this
0x18000f7a7  call    ?IsWithinInterval@CSchedule@@AEAAHAEBVTimeValue@@@Z; CSchedule::IsWithinInterval(TimeValue const &)
0x18000f7ac  xor     edx, edx
0x18000f7ae  test    eax, eax
0x18000f7b0  setz    dl
0x18000f7b3  jmp     short loc_18000F7B7
0x18000f7b5  xor     edx, edx
0x18000f7b7  mov     [rbx+108h], edx
0x18000f7bd  add     rsp, 50h
0x18000f7c1  pop     rbx
0x18000f7c2  retn
```
