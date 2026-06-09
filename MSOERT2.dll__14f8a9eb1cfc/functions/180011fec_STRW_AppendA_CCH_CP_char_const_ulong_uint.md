# STRW::AppendA_CCH_CP(char const *,ulong,uint)

- ea: `0x180011fec`
- end: `0x1800120c1`
- name: `?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z`
- size: `213`
- prototype: `__int64 __fastcall(STRW *__hidden this, const char *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a9f0`
- `0x18000b390`
- `0x18000e9b0`
- `0x18000f500`
- `0x18000f5c0`
- `0x18000f8e0`

## callees

- `0x1800092d4`
- `0x180009378`
- `0x1800119b4`
- `0x180011fb8`
- `0x180011fec`
- `0x180012168`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall STRW::AppendA_CCH_CP(STRW *this, const char *a2, int a3)
{
  int v3; // ebx
  unsigned __int64 v7; // r8
  unsigned int v8; // ecx
  unsigned int v10; // [rsp+30h] [rbp-468h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-460h] BYREF
  unsigned __int16 *v12[4]; // [rsp+40h] [rbp-458h] BYREF
  unsigned __int16 v13[520]; // [rsp+60h] [rbp-438h] BYREF

  v3 = 0;
  if ( a2 && a3 )
  {
    STRW::STRW((STRW *)&v11, v13, 0x208u);
    v3 = BUFFER::Reserve((BUFFER *)v12, (unsigned int)(3 * a3) + 2LL, v7);
    if ( v3 >= 0 )
    {
      v10 = 0;
      v3 = HrSHAnsiToUnicodeCP(v8, a2, v12[0], (unsigned __int64)v12[1] >> 1, &v10);
      if ( v3 >= 0 )
      {
        v11 = v10;
        v3 = STRW::Append(this, (const struct STRW *)&v11);
      }
    }
    STRW::~STRW((STRW *)&v11);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011fec  mov     [rsp+arg_18], rbx
0x180011ff1  push    rbp
0x180011ff2  push    rsi
0x180011ff3  push    rdi
0x180011ff4  sub     rsp, 480h
0x180011ffb  mov     rax, cs:__security_cookie
0x180012002  xor     rax, rsp
0x180012005  mov     [rsp+498h+var_28], rax
0x18001200d  xor     ebx, ebx
0x18001200f  mov     edi, r8d
0x180012012  mov     rsi, rdx
0x180012015  mov     rbp, rcx
0x180012018  test    rdx, rdx
0x18001201b  jz      short loc_18001209C
0x18001201d  test    r8d, r8d
0x180012020  jz      short loc_18001209C
0x180012022  mov     r8d, 208h; unsigned int
0x180012028  lea     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18001202d  lea     rcx, [rsp+498h+var_460]; this
0x180012032  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180012037  lea     edx, [rdi+rdi*2]
0x18001203a  add     rdx, 2; unsigned __int64
0x18001203e  lea     rcx, [rsp+498h+var_458]; this
0x180012043  call    ?Reserve@BUFFER@@QEAAJ_K0@Z; BUFFER::Reserve(unsigned __int64,unsigned __int64)
0x180012048  mov     ebx, eax
0x18001204a  test    eax, eax
0x18001204c  js      short loc_180012092
0x18001204e  mov     r9, [rsp+498h+var_450]
0x180012053  lea     rax, [rsp+498h+var_468]
0x180012058  mov     r8, [rsp+498h+var_458]; unsigned __int16 *
0x18001205d  mov     rdx, rsi; char *
0x180012060  shr     r9, 1; int
0x180012063  mov     [rsp+498h+var_468], 0
0x18001206b  mov     [rsp+498h+var_478], rax; unsigned int *
0x180012070  call    ?HrSHAnsiToUnicodeCP@@YAJIPEBDPEAGHPEAK@Z; HrSHAnsiToUnicodeCP(uint,char const *,ushort *,int,ulong *)
0x180012075  mov     ebx, eax
0x180012077  test    eax, eax
0x180012079  js      short loc_180012092
0x18001207b  mov     eax, [rsp+498h+var_468]
0x18001207f  lea     rdx, [rsp+498h+var_460]; struct STRW *
0x180012084  mov     rcx, rbp; this
0x180012087  mov     [rsp+498h+var_460], eax
0x18001208b  call    ?Append@STRW@@QEAAJPEBV1@@Z; STRW::Append(STRW const *)
0x180012090  mov     ebx, eax
0x180012092  lea     rcx, [rsp+498h+var_460]; this
0x180012097  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18001209c  mov     eax, ebx
0x18001209e  mov     rcx, [rsp+498h+var_28]
0x1800120a6  xor     rcx, rsp; StackCookie
0x1800120a9  call    __security_check_cookie
0x1800120ae  mov     rbx, [rsp+498h+arg_18]
0x1800120b6  add     rsp, 480h
0x1800120bd  pop     rdi
0x1800120be  pop     rsi
0x1800120bf  pop     rbp
0x1800120c0  retn
```
