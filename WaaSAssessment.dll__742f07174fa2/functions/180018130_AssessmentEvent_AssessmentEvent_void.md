# AssessmentEvent::~AssessmentEvent(void)

- ea: `0x180018130`
- end: `0x18001822e`
- name: `??1AssessmentEvent@@QEAA@XZ`
- size: `254`
- prototype: `void __fastcall(AssessmentEvent *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007aa0`
- `0x180008220`
- `0x180008310`
- `0x1800086e0`
- `0x1800087d0`
- `0x1800088d0`

## callees

- `0x180017244`
- `0x1800177f0`
- `0x180018130`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018217`

## pseudocode

```c
void __fastcall AssessmentEvent::~AssessmentEvent(AssessmentEvent *this)
{
  unsigned int v2; // r9d
  const char *v3; // rcx
  int v4; // r8d
  const unsigned __int16 *v5; // rdx
  int v6; // r9d
  int v7; // r10d
  int v8; // r11d
  void *v9; // rcx

  if ( *(_DWORD *)this )
  {
    v2 = *((_DWORD *)this + 39);
    v3 = (char *)this + 8;
    v4 = *((_DWORD *)this + 40);
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 18);
    if ( v2 - 2 <= 1 )
    {
      v7 = *((_DWORD *)this + 38);
      v8 = *((_DWORD *)this + 41);
      if ( *((_DWORD *)this + 1) )
        LogAssessmentStop(v3, v5, v4, v2, v8, v7, *((_DWORD *)this + 42), *((_DWORD *)this + 43));
      else
        LogAssessmentStop(v3, v5, v4, v2, v8, v7, 0, 0);
    }
    else
    {
      v6 = *((_DWORD *)this + 38);
      if ( *((_DWORD *)this + 1) )
        LogOSAssessmentStop(
          v3,
          v5,
          v4,
          v6,
          *((_DWORD *)this + 44),
          *((_DWORD *)this + 45),
          *((_DWORD *)this + 46),
          *((_DWORD *)this + 47));
      else
        LogOSAssessmentStop(v3, v5, v4, v6, 0, 0, 0, 0);
    }
  }
  v9 = (void *)*((_QWORD *)this + 18);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x180018130  push    rbx
0x180018132  sub     rsp, 40h
0x180018136  cmp     dword ptr [rcx], 0
0x180018139  mov     rbx, rcx
0x18001813c  jz      loc_18001820B
0x180018142  mov     r9d, [rcx+9Ch]; unsigned int
0x180018149  add     rcx, 8; char *
0x18001814d  mov     r8d, [rbx+0A0h]; int
0x180018154  mov     rdx, [rbx+90h]; unsigned __int16 *
0x18001815b  lea     eax, [r9-2]
0x18001815f  cmp     eax, 1
0x180018162  jbe     short loc_1800181C2
0x180018164  cmp     dword ptr [rbx+4], 0
0x180018168  mov     r9d, [rbx+98h]; int
0x18001816f  jz      short loc_18001819B
0x180018171  mov     eax, [rbx+0BCh]
0x180018177  mov     [rsp+48h+var_10], eax
0x18001817b  mov     eax, [rbx+0B8h]
0x180018181  mov     [rsp+48h+var_18], eax
0x180018185  mov     eax, [rbx+0B4h]
0x18001818b  mov     [rsp+48h+var_20], eax
0x18001818f  mov     eax, [rbx+0B0h]
0x180018195  mov     [rsp+48h+var_28], eax
0x180018199  jmp     short loc_1800181BB
0x18001819b  mov     [rsp+48h+var_10], 0; unsigned int
0x1800181a3  mov     [rsp+48h+var_18], 0; unsigned int
0x1800181ab  mov     [rsp+48h+var_20], 0; unsigned int
0x1800181b3  mov     [rsp+48h+var_28], 0; unsigned int
0x1800181bb  call    ?LogOSAssessmentStop@@YAXPEBDPEBGHJKKKK@Z; LogOSAssessmentStop(char const *,ushort const *,int,long,ulong,ulong,ulong,ulong)
0x1800181c0  jmp     short loc_18001820B
0x1800181c2  cmp     dword ptr [rbx+4], 0
0x1800181c6  mov     r10d, [rbx+98h]
0x1800181cd  mov     r11d, [rbx+0A4h]
0x1800181d4  jz      short loc_1800181EC
0x1800181d6  mov     eax, [rbx+0ACh]
0x1800181dc  mov     [rsp+48h+var_10], eax
0x1800181e0  mov     eax, [rbx+0A8h]
0x1800181e6  mov     [rsp+48h+var_18], eax
0x1800181ea  jmp     short loc_1800181FC
0x1800181ec  mov     [rsp+48h+var_10], 0; unsigned int
0x1800181f4  mov     [rsp+48h+var_18], 0; unsigned int
0x1800181fc  mov     [rsp+48h+var_20], r10d; int
0x180018201  mov     [rsp+48h+var_28], r11d; int
0x180018206  call    ?LogAssessmentStop@@YAXPEBDPEBGHKHJKK@Z; LogAssessmentStop(char const *,ushort const *,int,ulong,int,long,ulong,ulong)
0x18001820b  mov     rcx, [rbx+90h]; pv
0x180018212  test    rcx, rcx
0x180018215  jz      short loc_180018228
0x180018217  call    cs:__imp_CoTaskMemFree
0x18001821d  mov     qword ptr [rbx+90h], 0
0x180018228  add     rsp, 40h
0x18001822c  pop     rbx
0x18001822d  retn
```
