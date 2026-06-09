# AssessmentEvent::SetAssessmentEventData(long,int,int,tagUpdateAssessment *)

- ea: `0x180018430`
- end: `0x18001847a`
- name: `?SetAssessmentEventData@AssessmentEvent@@QEAAXJHHPEAUtagUpdateAssessment@@@Z`
- size: `74`
- prototype: `void __fastcall(AssessmentEvent *__hidden this, int, int, int, struct tagUpdateAssessment *)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007aa0`
- `0x180008220`
- `0x180008310`
- `0x1800086e0`

## callees

- `0x180018430`

## pseudocode

```c
void __fastcall AssessmentEvent::SetAssessmentEventData(
        AssessmentEvent *this,
        int a2,
        int a3,
        int a4,
        struct tagUpdateAssessment *a5)
{
  *((_DWORD *)this + 40) = a3;
  *((_DWORD *)this + 38) = a2;
  *((_DWORD *)this + 41) = a4;
  if ( !a5 || a2 < 0 || a2 == 1 )
  {
    *((_DWORD *)this + 1) = 0;
  }
  else
  {
    *((_DWORD *)this + 1) = 1;
    *((_DWORD *)this + 42) = a5->impact;
    *((_DWORD *)this + 43) = a5->status;
  }
}

```

## disassembly

```asm
0x180018430  mov     [rcx+0A0h], r8d
0x180018437  mov     r8, [rsp+arg_20]
0x18001843c  mov     [rcx+98h], edx
0x180018442  mov     [rcx+0A4h], r9d
0x180018449  test    r8, r8
0x18001844c  jz      short loc_180018472
0x18001844e  test    edx, edx
0x180018450  js      short loc_180018472
0x180018452  cmp     edx, 1
0x180018455  jz      short loc_180018472
0x180018457  mov     dword ptr [rcx+4], 1
0x18001845e  mov     eax, [r8+4]
0x180018462  mov     [rcx+0A8h], eax
0x180018468  mov     eax, [r8]
0x18001846b  mov     [rcx+0ACh], eax
0x180018471  retn
0x180018472  mov     dword ptr [rcx+4], 0
0x180018479  retn
```
