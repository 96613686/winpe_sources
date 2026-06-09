# Broker::CalculateDelay(_TB_IRREGULAR_SCHEDULE *,_ULARGE_INTEGER,_ULARGE_INTEGER *,ulong *)

- ea: `0x1800113dc`
- end: `0x18001152a`
- name: `?CalculateDelay@Broker@@YAHPEAU_TB_IRREGULAR_SCHEDULE@@T_ULARGE_INTEGER@@PEAT3@PEAK@Z`
- size: `334`
- prototype: `__int64 __fastcall(Broker *this, struct _SYSTEMTIME *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008c70`
- `0x180009750`

## callees

- `0x180003840`
- `0x1800113dc`
- `0x180012dd0`
- `0x180018c8c`
- `0x180018f9c`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800114ad`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800114eb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800114ad`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800114eb`

## pseudocode

```c
__int64 __fastcall Broker::CalculateDelay(
        Broker *this,
        struct _SYSTEMTIME *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4)
{
  int v9; // eax
  unsigned int v10; // r9d
  unsigned int WeeklyDelay; // eax
  FILETIME FileTime; // [rsp+20h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-18h] BYREF

  FileTime = 0;
  SystemTime = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7649fb1f806a34575f68b1593ffe1606_Traceguids);
  a4->LowPart = 0;
  if ( (unsigned __int64)a2 < *(_QWORD *)a3.QuadPart )
    return 0;
  v9 = *(_DWORD *)this;
  v10 = 1;
  if ( *(_DWORD *)this != 1 )
  {
    if ( v9 == 2 )
    {
      FileTime = *(FILETIME *)a3.QuadPart;
      if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
        return 0;
      WeeklyDelay = Broker::GetWeeklyDelay(
                      this,
                      (struct _TB_IRREGULAR_SCHEDULE *)&SystemTime,
                      a2,
                      (union _ULARGE_INTEGER)a4,
                      *(unsigned int **)&FileTime);
    }
    else
    {
      if ( (unsigned int)(v9 - 3) > 1 )
        return v10;
      FileTime = *(FILETIME *)a3.QuadPart;
      if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
        return 0;
      WeeklyDelay = Broker::GetMonthlyDelay(
                      this,
                      (struct _TB_IRREGULAR_SCHEDULE *)&SystemTime,
                      a2,
                      (union _ULARGE_INTEGER)a4,
                      *(unsigned int **)&FileTime);
    }
    return WeeklyDelay == 0;
  }
  a4->LowPart = 86400 * *((unsigned __int16 *)this + 4)
              - ((unsigned __int64)a2 - *(_QWORD *)a3.QuadPart)
              % (10000000 * (unsigned __int64)(86400 * (unsigned int)*((unsigned __int16 *)this + 4)))
              / 0x989680;
  return v10;
}

```

## disassembly

```asm
0x1800113dc  push    rbp
0x1800113de  push    rbx
0x1800113df  push    rsi
0x1800113e0  push    rdi
0x1800113e1  push    r14
0x1800113e3  mov     rbp, rsp
0x1800113e6  sub     rsp, 40h
0x1800113ea  mov     rax, cs:__security_cookie
0x1800113f1  xor     rax, rsp
0x1800113f4  mov     [rbp+var_8], rax
0x1800113f8  xorps   xmm0, xmm0
0x1800113fb  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180011403  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180011407  mov     rsi, r9
0x18001140a  mov     rdi, r8
0x18001140d  mov     rbx, rdx
0x180011410  mov     r14, rcx
0x180011413  mov     rcx, cs:WPP_GLOBAL_Control
0x18001141a  test    byte ptr [rcx+1Ch], 40h
0x18001141e  jz      short loc_18001143B
0x180011420  cmp     byte ptr [rcx+19h], 4
0x180011424  jb      short loc_18001143B
0x180011426  mov     rcx, [rcx+10h]
0x18001142a  lea     r8, WPP_7649fb1f806a34575f68b1593ffe1606_Traceguids
0x180011431  mov     edx, 0Ah
0x180011436  call    WPP_SF_
0x18001143b  mov     dword ptr [rsi], 0
0x180011441  cmp     rbx, [rdi]
0x180011444  jnb     short loc_18001144D
0x180011446  xor     eax, eax
0x180011448  jmp     loc_180011513
0x18001144d  mov     eax, [r14]
0x180011450  mov     r9d, 1
0x180011456  cmp     eax, r9d
0x180011459  jnz     short loc_180011495
0x18001145b  movzx   eax, word ptr [r14+8]
0x180011460  xor     edx, edx
0x180011462  sub     rbx, [rdi]
0x180011465  imul    r8d, eax, 15180h
0x18001146c  mov     eax, r8d
0x18001146f  imul    rcx, rax, 989680h
0x180011476  mov     rax, rbx
0x180011479  div     rcx
0x18001147c  mov     rax, 0D6BF94D5E57A42BDh
0x180011486  mul     rdx
0x180011489  shr     rdx, 17h
0x18001148d  sub     r8d, edx
0x180011490  mov     [rsi], r8d
0x180011493  jmp     short loc_180011510
0x180011495  cmp     eax, 2
0x180011498  jnz     short loc_1800114D0
0x18001149a  mov     eax, [rdi+4]
0x18001149d  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800114a1  mov     [rbp+FileTime.dwHighDateTime], eax
0x1800114a4  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800114a8  mov     eax, [rdi]
0x1800114aa  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800114ad  call    cs:__imp_FileTimeToSystemTime
0x1800114b3  test    eax, eax
0x1800114b5  jnz     short loc_1800114BC
0x1800114b7  xor     r9d, r9d
0x1800114ba  jmp     short loc_180011510
0x1800114bc  mov     r9, rsi; union _ULARGE_INTEGER
0x1800114bf  lea     rdx, [rbp+SystemTime]; struct _TB_IRREGULAR_SCHEDULE *
0x1800114c3  mov     r8, rbx; struct _SYSTEMTIME *
0x1800114c6  mov     rcx, r14; this
0x1800114c9  call    ?GetWeeklyDelay@Broker@@YAKPEAU_TB_IRREGULAR_SCHEDULE@@PEAU_SYSTEMTIME@@T_ULARGE_INTEGER@@PEAK@Z; Broker::GetWeeklyDelay(_TB_IRREGULAR_SCHEDULE *,_SYSTEMTIME *,_ULARGE_INTEGER,ulong *)
0x1800114ce  jmp     short loc_180011507
0x1800114d0  add     eax, 0FFFFFFFDh
0x1800114d3  cmp     eax, r9d
0x1800114d6  ja      short loc_180011510
0x1800114d8  mov     eax, [rdi+4]
0x1800114db  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800114df  mov     [rbp+FileTime.dwHighDateTime], eax
0x1800114e2  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800114e6  mov     eax, [rdi]
0x1800114e8  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800114eb  call    cs:__imp_FileTimeToSystemTime
0x1800114f1  test    eax, eax
0x1800114f3  jz      short loc_1800114B7
0x1800114f5  mov     r9, rsi; union _ULARGE_INTEGER
0x1800114f8  lea     rdx, [rbp+SystemTime]; struct _TB_IRREGULAR_SCHEDULE *
0x1800114fc  mov     r8, rbx; struct _SYSTEMTIME *
0x1800114ff  mov     rcx, r14; this
0x180011502  call    ?GetMonthlyDelay@Broker@@YAKPEAU_TB_IRREGULAR_SCHEDULE@@PEAU_SYSTEMTIME@@T_ULARGE_INTEGER@@PEAK@Z; Broker::GetMonthlyDelay(_TB_IRREGULAR_SCHEDULE *,_SYSTEMTIME *,_ULARGE_INTEGER,ulong *)
0x180011507  xor     r9d, r9d
0x18001150a  test    eax, eax
0x18001150c  setz    r9b
0x180011510  mov     eax, r9d
0x180011513  mov     rcx, [rbp+var_8]
0x180011517  xor     rcx, rsp; StackCookie
0x18001151a  call    __security_check_cookie
0x18001151f  add     rsp, 40h
0x180011523  pop     r14
0x180011525  pop     rdi
0x180011526  pop     rsi
0x180011527  pop     rbx
0x180011528  pop     rbp
0x180011529  retn
```
