# ComputeTimeMsHistogramStats<MakeResidentStatistics>(TimeMsHistogram const &)

- ea: `0x1800255a4`
- end: `0x180025673`
- name: `??$ComputeTimeMsHistogramStats@UMakeResidentStatistics@@@@YA?AUMakeResidentStatistics@@AEBVTimeMsHistogram@@@Z`
- size: `207`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800258a0`

## callees

- `0x1800047f0`
- `0x180004b41`
- `0x1800253cc`
- `0x1800255a4`

## pseudocode

```c
_QWORD *__fastcall ComputeTimeMsHistogramStats<MakeResidentStatistics>(_QWORD *a1, __int64 *a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int64 v7; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  memset_0(a1 + 5, 0, 0xA0u);
  a1[25] = 0;
  if ( *((_DWORD *)a2 + 8) )
    v5 = *a2;
  else
    v5 = 0;
  a1[1] = v5;
  if ( *((_DWORD *)a2 + 8) )
    v6 = a2[1];
  else
    v6 = 0;
  a1[2] = v6;
  *a1 = *((unsigned int *)a2 + 8);
  if ( *((_DWORD *)a2 + 8) )
  {
    v7 = a2[2] / (unsigned __int64)*((unsigned int *)a2 + 8);
    v4 = a2[2] % (unsigned __int64)*((unsigned int *)a2 + 8);
  }
  else
  {
    v7 = 0;
  }
  a1[3] = v7;
  a1[4] = gpm::statistics::averages<unsigned __int64>::variance(a2 + 2, v4);
  memmove_0(a1 + 5, (const void *)a2[9], a2[10] - a2[9]);
  return a1;
}

```

## disassembly

```asm
0x1800255a4  mov     [rsp+arg_0], rbx
0x1800255a9  mov     [rsp+arg_8], rsi
0x1800255ae  push    rdi
0x1800255af  sub     rsp, 20h
0x1800255b3  mov     rdi, rdx
0x1800255b6  mov     qword ptr [rcx], 0
0x1800255bd  mov     rbx, rcx
0x1800255c0  mov     qword ptr [rcx+8], 0
0x1800255c8  mov     qword ptr [rcx+10h], 0
0x1800255d0  xor     edx, edx; Val
0x1800255d2  mov     qword ptr [rcx+18h], 0
0x1800255da  mov     r8d, 0A0h; Size
0x1800255e0  mov     qword ptr [rcx+20h], 0
0x1800255e8  add     rcx, 28h ; '('; void *
0x1800255ec  call    memset_0
0x1800255f1  mov     qword ptr [rbx+0C8h], 0
0x1800255fc  cmp     dword ptr [rdi+20h], 0
0x180025600  jbe     short loc_180025607
0x180025602  mov     rax, [rdi]
0x180025605  jmp     short loc_180025609
0x180025607  xor     eax, eax
0x180025609  mov     [rbx+8], rax
0x18002560d  cmp     dword ptr [rdi+20h], 0
0x180025611  jbe     short loc_180025619
0x180025613  mov     rax, [rdi+8]
0x180025617  jmp     short loc_18002561B
0x180025619  xor     eax, eax
0x18002561b  mov     [rbx+10h], rax
0x18002561f  mov     eax, [rdi+20h]
0x180025622  mov     [rbx], rax
0x180025625  cmp     dword ptr [rdi+20h], 0
0x180025629  jz      short loc_180025639
0x18002562b  mov     ecx, [rdi+20h]
0x18002562e  xor     edx, edx
0x180025630  mov     rax, [rdi+10h]
0x180025634  div     rcx
0x180025637  jmp     short loc_18002563B
0x180025639  xor     eax, eax
0x18002563b  lea     rcx, [rdi+10h]
0x18002563f  mov     [rbx+18h], rax
0x180025643  call    ?variance@?$averages@_K@statistics@gpm@@QEBA_KXZ; gpm::statistics::averages<unsigned __int64>::variance(void)
0x180025648  mov     [rbx+20h], rax
0x18002564c  lea     rcx, [rbx+28h]; void *
0x180025650  mov     rdx, [rdi+48h]; Src
0x180025654  mov     r8, [rdi+50h]
0x180025658  sub     r8, rdx; Size
0x18002565b  call    memmove_0
0x180025660  mov     rsi, [rsp+28h+arg_8]
0x180025665  mov     rax, rbx
0x180025668  mov     rbx, [rsp+28h+arg_0]
0x18002566d  add     rsp, 20h
0x180025671  pop     rdi
0x180025672  retn
```
