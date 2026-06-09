# CRegistry::DeleteSubKeyTree(wchar_t const *)

- ea: `0x140028890`
- end: `0x140028a67`
- name: `?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z`
- size: `471`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140028890`

## callees

- `0x1400030a0`
- `0x1400280d4`
- `0x1400284e8`
- `0x140028588`
- `0x1400286d4`
- `0x140028844`
- `0x140028890`
- `0x140028ab8`
- `0x1400292a8`
- `0x140029ab8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400288c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400288c6`

## string_xrefs

- `0x140028940`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegistry::DeleteSubKeyTree(CRegistry *this, const wchar_t *a2)
{
  __int64 v4; // r8
  __int64 i; // rcx
  __int64 v6; // rcx
  __int64 v7; // r9
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 result; // rax
  unsigned int v12; // edx
  unsigned int v13; // [rsp+20h] [rbp-378h] BYREF
  void **v14; // [rsp+28h] [rbp-370h]
  const wchar_t *v15; // [rsp+30h] [rbp-368h]
  int v16; // [rsp+38h] [rbp-360h]
  int v17; // [rsp+3Ch] [rbp-35Ch]
  __int64 v18; // [rsp+40h] [rbp-358h]
  void **v19; // [rsp+50h] [rbp-348h] BYREF
  wchar_t *v20; // [rsp+58h] [rbp-340h]
  int v21; // [rsp+60h] [rbp-338h]
  char v22; // [rsp+68h] [rbp-330h] BYREF
  _BYTE v23[192]; // [rsp+B0h] [rbp-2E8h] BYREF
  wchar_t v24[264]; // [rsp+170h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  v18 = -2;
  SetLastError(0);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v17 = v4;
  v16 = v4;
  v15 = a2;
  v14 = &CConstString::`vftable';
  for ( i = (unsigned int)(v4 - 1); (int)i >= 0; i = (unsigned int)(i - 1) )
  {
    if ( a2[i] == 47 )
      break;
    if ( a2[i] == 92 )
      break;
  }
  v6 = (unsigned int)(i + 1);
  v7 = (unsigned int)(v4 - v6);
  v8 = (unsigned int)v6;
  v9 = v7 + v6;
  if ( v9 < v8 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( v9 > (unsigned int)v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v13);
  v19 = &CLMString::`vftable';
  v20 = (wchar_t *)&v22;
  v21 = 33;
  CLMString::AssignInConstructor((void **)&v19, &a2[v8], v7);
  v19 = &TLMString<32,32,1024>::`vftable';
  v13 = 0;
  try
  {
    CRegistry::CRegistry((CRegistry *)v23, this, v20, 0xF003Fu);
    do
    {
      v13 = 260;
      if ( !CRegistry::EnumSubKey((CRegistry *)v23, v12, v24, &v13) )
      {
        CRegistry::~CRegistry((CRegistry *)v23);
        v10 = CRegistry::DeleteSubKey(this, v20);
        TLMString<32,32,1024>::~TLMString<32,32,1024>(&v19);
        return v10;
      }
    }
    while ( (unsigned int)CRegistry::DeleteSubKeyTree((CRegistry *)v23, v24) );
    CRegistry::~CRegistry((CRegistry *)v23);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v19);
    result = 0;
  }
  catch ( ... )
  {
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v19);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140028890  mov     rax, rsp
0x140028893  push    rdi
0x140028894  sub     rsp, 390h
0x14002889b  mov     [rsp+398h+var_358], 0FFFFFFFFFFFFFFFEh
0x1400288a4  mov     [rax+10h], rbx
0x1400288a8  mov     [rax+18h], rsi
0x1400288ac  mov     rax, cs:__security_cookie
0x1400288b3  xor     rax, rsp
0x1400288b6  mov     [rsp+398h+var_18], rax
0x1400288be  mov     rbx, rdx
0x1400288c1  mov     rdi, rcx
0x1400288c4  xor     ecx, ecx; dwErrCode
0x1400288c6  call    cs:__imp_SetLastError
0x1400288cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400288d0  xor     esi, esi
0x1400288d2  inc     r8
0x1400288d5  cmp     [rbx+r8*2], si
0x1400288da  jnz     short loc_1400288D2
0x1400288dc  mov     [rsp+398h+var_35C], r8d
0x1400288e1  mov     [rsp+398h+var_360], r8d
0x1400288e6  mov     [rsp+398h+var_368], rbx
0x1400288eb  lea     rax, ??_7CConstString@@6B@; const CConstString::`vftable'
0x1400288f2  mov     [rsp+398h+var_370], rax
0x1400288f7  lea     ecx, [r8-1]
0x1400288fb  test    ecx, ecx
0x1400288fd  js      short loc_140028912
0x1400288ff  cmp     word ptr [rbx+rcx*2], 2Fh ; '/'
0x140028904  jz      short loc_140028912
0x140028906  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x14002890b  jz      short loc_140028912
0x14002890d  sub     ecx, 1
0x140028910  jns     short loc_1400288FF
0x140028912  inc     ecx
0x140028914  mov     r9d, r8d
0x140028917  sub     r9d, ecx
0x14002891a  mov     edx, ecx
0x14002891c  add     rcx, r9
0x14002891f  cmp     rcx, rdx
0x140028922  jnb     short loc_14002892A
0x140028924  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x14002892a  mov     eax, r8d
0x14002892d  cmp     rcx, rax
0x140028930  jbe     short loc_140028952
0x140028932  mov     rcx, [rsp+398h]; this
0x14002893a  mov     r9d, 0CEh; char *
0x140028940  lea     r8, aOnecoreuapBase_39; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140028947  mov     edx, 40Ch; void *
0x14002894c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140028952  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x140028959  mov     [rsp+398h+var_348], rax
0x14002895e  lea     rax, [rsp+398h+var_330]
0x140028963  mov     [rsp+398h+var_340], rax
0x140028968  mov     [rsp+398h+var_338], 21h ; '!'
0x140028970  lea     rdx, [rbx+rdx*2]; wchar_t *
0x140028974  mov     r8d, r9d; unsigned int
0x140028977  lea     rcx, [rsp+398h+var_348]; this
0x14002897c  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x140028981  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x140028988  mov     [rsp+398h+var_348], rax
0x14002898d  mov     [rsp+398h+var_378], esi
0x140028991  mov     r9d, 0F003Fh; unsigned int
0x140028997  mov     r8, [rsp+398h+var_340]; wchar_t *
0x14002899c  mov     rdx, rdi; struct CRegistry *
0x14002899f  lea     rcx, [rsp+398h+var_2E8]; this
0x1400289a7  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x1400289ac  nop
0x1400289ad  mov     [rsp+398h+var_378], 104h; unsigned int
0x1400289b5  lea     r9, [rsp+398h+var_378]; unsigned int *
0x1400289ba  lea     r8, [rsp+398h+var_228]; wchar_t *
0x1400289c2  lea     rcx, [rsp+398h+var_2E8]; this
0x1400289ca  call    ?EnumSubKey@CRegistry@@QEAAHIPEA_WPEAK@Z; CRegistry::EnumSubKey(uint,wchar_t *,ulong *)
0x1400289cf  test    eax, eax
0x1400289d1  jnz     short loc_1400289FF
0x1400289d3  lea     rcx, [rsp+398h+var_2E8]; this
0x1400289db  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1400289e0  nop
0x1400289e1  mov     rdx, [rsp+398h+var_340]; wchar_t *
0x1400289e6  mov     rcx, rdi; this
0x1400289e9  call    ?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z; CRegistry::DeleteSubKey(wchar_t const *)
0x1400289ee  mov     ebx, eax
0x1400289f0  lea     rcx, [rsp+398h+var_348]
0x1400289f5  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1400289fa  nop
0x1400289fb  mov     eax, ebx
0x1400289fd  jmp     short loc_140028A42
0x1400289ff  lea     rdx, [rsp+398h+var_228]; wchar_t *
0x140028a07  lea     rcx, [rsp+398h+var_2E8]; this
0x140028a0f  call    ?DeleteSubKeyTree@CRegistry@@UEAAHPEB_W@Z; CRegistry::DeleteSubKeyTree(wchar_t const *)
0x140028a14  test    eax, eax
0x140028a16  jnz     short loc_1400289AD
0x140028a18  lea     rcx, [rsp+398h+var_2E8]; this
0x140028a20  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x140028a25  nop
0x140028a26  lea     rcx, [rsp+398h+var_348]
0x140028a2b  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x140028a30  nop
0x140028a31  xor     eax, eax
0x140028a33  jmp     short loc_140028A42
0x140028a35  lea     rcx, [rsp+398h+var_348]
0x140028a3a  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x140028a3f  nop
0x140028a40  xor     eax, eax
0x140028a42  mov     rcx, [rsp+398h+var_18]
0x140028a4a  xor     rcx, rsp; StackCookie
0x140028a4d  call    __security_check_cookie
0x140028a52  lea     r11, [rsp+398h+var_8]
0x140028a5a  mov     rbx, [r11+18h]
0x140028a5e  mov     rsi, [r11+20h]
0x140028a62  mov     rsp, r11
0x140028a65  pop     rdi
0x140028a66  retn
```
