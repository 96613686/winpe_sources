# CEnumerateFileTimeByCalendar::MoveNext(void)

- ea: `0x18007f650`
- end: `0x18007f795`
- name: `?MoveNext@CEnumerateFileTimeByCalendar@@UEAAJXZ`
- size: `325`
- prototype: `__int64 __fastcall(CEnumerateFileTimeByCalendar *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18007f650`
- `0x1800c3154`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007f740`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007f740`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007f75b`
- `api-ms-win-core-calendar-l1-1-0!AdjustCalendarDate` at `0x18007f75b`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18007f6bd`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18007f6f0`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18007f6bd`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18007f6f0`

## pseudocode

```c
_BOOL8 __fastcall CEnumerateFileTimeByCalendar::MoveNext(CEnumerateFileTimeByCalendar *this)
{
  _DWORD *v1; // rdi
  _DWORD *v3; // rsi
  bool v4; // zf
  int v5; // ebp
  int v6; // eax
  const FILETIME *v7; // r15
  _BOOL8 result; // rax
  char *v9; // r14

  v1 = (_DWORD *)((char *)this + 88);
  v3 = (_DWORD *)((char *)this + 16);
  if ( !*((_DWORD *)this + 5) )
  {
    v9 = (char *)this + 80;
    v7 = (const FILETIME *)((char *)this + 72);
    *((_QWORD *)this + 9) = *((_QWORD *)this + 10);
    return CompareFileTime(v7, (const FILETIME *)this + 8) > 0
        || !(unsigned int)AdjustCalendarDate(v1, (unsigned int)(*v3 != 0) + 1, 1)
        || (int)ConvertFromCalDateTimeHelper(v1, 516, v9, 257) < 0;
  }
  v4 = *v3 == 0;
  v5 = 1;
  *v1 = *((_DWORD *)this + 3);
  *((_DWORD *)this + 23) = *((_DWORD *)this + 7);
  *((_DWORD *)this + 24) = *((_DWORD *)this + 8);
  v6 = 1;
  if ( !v4 )
    v6 = *((_DWORD *)this + 9);
  *((_DWORD *)this + 25) = v6;
  v7 = (const FILETIME *)((char *)this + 72);
  *((_DWORD *)this + 26) = 1;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( (unsigned int)UpdateCalendarDayOfWeek(v1) && (int)ConvertFromCalDateTimeHelper(v1, 516, v7, 257) >= 0
    || (*v3 ? ++*((_DWORD *)this + 25) : ++*((_DWORD *)this + 24),
        (unsigned int)UpdateCalendarDayOfWeek(v1) && (int)ConvertFromCalDateTimeHelper(v1, 516, v7, 257) >= 0) )
  {
    result = 0;
  }
  else
  {
    v5 = 0;
    result = 1;
  }
  *((_DWORD *)this + 5) = 0;
  if ( v5 )
  {
    v9 = (char *)this + 80;
    return CompareFileTime(v7, (const FILETIME *)this + 8) > 0
        || !(unsigned int)AdjustCalendarDate(v1, (unsigned int)(*v3 != 0) + 1, 1)
        || (int)ConvertFromCalDateTimeHelper(v1, 516, v9, 257) < 0;
  }
  return result;
}

```

## disassembly

```asm
0x18007f650  push    rbx
0x18007f652  push    rbp
0x18007f653  push    rsi
0x18007f654  push    rdi
0x18007f655  push    r13
0x18007f657  push    r14
0x18007f659  push    r15
0x18007f65b  sub     rsp, 20h
0x18007f65f  cmp     dword ptr [rcx+14h], 0
0x18007f663  lea     rdi, [rcx+58h]
0x18007f667  mov     rbx, rcx
0x18007f66a  lea     rsi, [rcx+10h]
0x18007f66e  mov     r13d, 1
0x18007f674  mov     r14d, 101h
0x18007f67a  jz      loc_18007F72B
0x18007f680  cmp     dword ptr [rsi], 0
0x18007f683  mov     ebp, r13d
0x18007f686  mov     eax, [rcx+0Ch]
0x18007f689  mov     [rdi], eax
0x18007f68b  mov     eax, [rcx+1Ch]
0x18007f68e  mov     [rcx+5Ch], eax
0x18007f691  mov     eax, [rcx+20h]
0x18007f694  mov     [rcx+60h], eax
0x18007f697  mov     eax, r13d
0x18007f69a  jz      short loc_18007F69F
0x18007f69c  mov     eax, [rcx+24h]
0x18007f69f  mov     [rcx+64h], eax
0x18007f6a2  lea     r15, [rcx+48h]
0x18007f6a6  mov     [rcx+68h], r13d
0x18007f6aa  mov     qword ptr [rcx+70h], 0
0x18007f6b2  mov     qword ptr [rcx+78h], 0
0x18007f6ba  mov     rcx, rdi
0x18007f6bd  call    cs:__imp_UpdateCalendarDayOfWeek
0x18007f6c3  test    eax, eax
0x18007f6c5  jz      short loc_18007F6DE
0x18007f6c7  mov     r9d, r14d
0x18007f6ca  mov     r8, r15
0x18007f6cd  mov     edx, 204h
0x18007f6d2  mov     rcx, rdi
0x18007f6d5  call    _ConvertFromCalDateTimeHelper
0x18007f6da  test    eax, eax
0x18007f6dc  jns     short loc_18007F711
0x18007f6de  cmp     dword ptr [rsi], 0
0x18007f6e1  jnz     short loc_18007F6E9
0x18007f6e3  add     [rbx+60h], r13d
0x18007f6e7  jmp     short loc_18007F6ED
0x18007f6e9  add     [rbx+64h], r13d
0x18007f6ed  mov     rcx, rdi
0x18007f6f0  call    cs:__imp_UpdateCalendarDayOfWeek
0x18007f6f6  test    eax, eax
0x18007f6f8  jz      short loc_18007F715
0x18007f6fa  mov     r9d, r14d
0x18007f6fd  mov     r8, r15
0x18007f700  mov     edx, 204h
0x18007f705  mov     rcx, rdi
0x18007f708  call    _ConvertFromCalDateTimeHelper
0x18007f70d  test    eax, eax
0x18007f70f  js      short loc_18007F715
0x18007f711  xor     eax, eax
0x18007f713  jmp     short loc_18007F71A
0x18007f715  xor     ebp, ebp
0x18007f717  mov     eax, r13d
0x18007f71a  mov     dword ptr [rbx+14h], 0
0x18007f721  test    ebp, ebp
0x18007f723  jz      short loc_18007F786
0x18007f725  lea     r14, [rbx+50h]
0x18007f729  jmp     short loc_18007F739
0x18007f72b  lea     r14, [rcx+50h]
0x18007f72f  mov     rax, [r14]
0x18007f732  lea     r15, [rcx+48h]
0x18007f736  mov     [r15], rax
0x18007f739  lea     rdx, [rbx+40h]; lpFileTime2
0x18007f73d  mov     rcx, r15; lpFileTime1
0x18007f740  call    cs:__imp_CompareFileTime
0x18007f746  test    eax, eax
0x18007f748  jg      short loc_18007F783
0x18007f74a  mov     eax, [rsi]
0x18007f74c  mov     r8d, r13d
0x18007f74f  neg     eax
0x18007f751  mov     rcx, rdi
0x18007f754  sbb     edx, edx
0x18007f756  neg     edx
0x18007f758  add     edx, r13d
0x18007f75b  call    cs:__imp_AdjustCalendarDate
0x18007f761  test    eax, eax
0x18007f763  jz      short loc_18007F783
0x18007f765  mov     r9d, 101h
0x18007f76b  mov     r8, r14
0x18007f76e  mov     edx, 204h
0x18007f773  mov     rcx, rdi
0x18007f776  call    _ConvertFromCalDateTimeHelper
0x18007f77b  test    eax, eax
0x18007f77d  js      short loc_18007F783
0x18007f77f  xor     eax, eax
0x18007f781  jmp     short loc_18007F786
0x18007f783  mov     eax, r13d
0x18007f786  add     rsp, 20h
0x18007f78a  pop     r15
0x18007f78c  pop     r14
0x18007f78e  pop     r13
0x18007f790  pop     rdi
0x18007f791  pop     rsi
0x18007f792  pop     rbp
0x18007f793  pop     rbx
0x18007f794  retn
```
