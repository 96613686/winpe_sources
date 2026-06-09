# AccessibilityCplCore::SaveSimpleATs(DirectUI::Element *)

- ea: `0x180017360`
- end: `0x18001745e`
- name: `?SaveSimpleATs@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015eb4`

## callees

- `0x180004f78`
- `0x180017360`
- `0x18001aab0`
- `0x18001af04`
- `0x18001fe70`
- `0x180020edc`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `KERNEL32!GetAtomNameW` at `0x1800173cc`
- `KERNEL32!GetAtomNameW` at `0x1800173cc`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18001738a`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18001738a`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800173b3`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800173b3`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800173e9`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800173e9`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SaveSimpleATs(AccessibilityCplCore *this, struct DirectUI::Element *a2)
{
  DirectUI::Element *Parent; // rbx
  ATOM ID; // ax
  struct Accommodation *v6; // rax
  Accommodation *v7; // rbx
  WCHAR Buffer[128]; // [rsp+30h] [rbp-128h] BYREF

  Parent = DirectUI::Element::GetParent(a2);
  if ( !Parent )
    return 2147500037LL;
  memset_0(Buffer, 0, sizeof(Buffer));
  ID = DirectUI::Element::GetID(Parent);
  if ( !ID )
    return 2147500037LL;
  if ( GetAtomNameW(ID, Buffer, 128) )
  {
    if ( (unsigned int)SettingIDFromName(Buffer) )
    {
      DirectUI::Element::GetSelected(a2);
      AccessibilityCplCore::VisitBOOLSetting(this);
    }
    v6 = Accommodation::Open(Buffer);
    v7 = v6;
    if ( v6 )
    {
      AccessibilityCplCore::ToggleAT(this, (const wchar_t **)v6, a2, *((_DWORD *)v6 + 20) != 1, 1);
      Accommodation::`scalar deleting destructor'(v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017360  mov     [rsp+arg_10], rbx
0x180017365  push    rbp
0x180017366  push    rsi
0x180017367  push    rdi
0x180017368  sub     rsp, 140h
0x18001736f  mov     rax, cs:__security_cookie
0x180017376  xor     rax, rsp
0x180017379  mov     [rsp+158h+var_28], rax
0x180017381  mov     rsi, rcx
0x180017384  mov     rdi, rdx
0x180017387  mov     rcx, rdx
0x18001738a  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180017390  xor     ebp, ebp
0x180017392  mov     rbx, rax
0x180017395  test    rax, rax
0x180017398  jz      loc_180017436
0x18001739e  xor     edx, edx; Val
0x1800173a0  lea     rcx, [rsp+158h+Buffer]; void *
0x1800173a5  mov     r8d, 100h; Size
0x1800173ab  call    memset_0
0x1800173b0  mov     rcx, rbx
0x1800173b3  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800173b9  test    ax, ax
0x1800173bc  jz      short loc_180017436
0x1800173be  mov     r8d, 80h; nSize
0x1800173c4  lea     rdx, [rsp+158h+Buffer]; lpBuffer
0x1800173c9  movzx   ecx, ax; nAtom
0x1800173cc  call    cs:__imp_GetAtomNameW
0x1800173d2  test    eax, eax
0x1800173d4  jz      short loc_180017432
0x1800173d6  lea     rcx, [rsp+158h+Buffer]
0x1800173db  call    ?SettingIDFromName@@YA?AW4CPL_SETTING_ID@@PEBG@Z; SettingIDFromName(ushort const *)
0x1800173e0  mov     ebx, eax
0x1800173e2  test    eax, eax
0x1800173e4  jz      short loc_1800173FD
0x1800173e6  mov     rcx, rdi
0x1800173e9  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800173ef  movzx   r8d, al; int
0x1800173f3  mov     edx, ebx; unsigned int
0x1800173f5  mov     rcx, rsi; this
0x1800173f8  call    ?VisitBOOLSetting@AccessibilityCplCore@@AEAAXKH@Z; AccessibilityCplCore::VisitBOOLSetting(ulong,int)
0x1800173fd  lea     rcx, [rsp+158h+Buffer]; unsigned __int16 *
0x180017402  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180017407  mov     rbx, rax
0x18001740a  test    rax, rax
0x18001740d  jz      short loc_180017432
0x18001740f  cmp     dword ptr [rax+50h], 1
0x180017413  mov     r8, rdi; struct DirectUI::Element *
0x180017416  mov     rdx, rax; struct Accommodation *
0x180017419  mov     [rsp+158h+var_138], 1; bool
0x18001741e  setnz   r9b; bool
0x180017422  mov     rcx, rsi; this
0x180017425  call    ?ToggleAT@AccessibilityCplCore@@AEAAJPEAVAccommodation@@PEAVElement@DirectUI@@_N2@Z; AccessibilityCplCore::ToggleAT(Accommodation *,DirectUI::Element *,bool,bool)
0x18001742a  mov     rcx, rbx; this
0x18001742d  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180017432  xor     eax, eax
0x180017434  jmp     short loc_18001743B
0x180017436  mov     eax, 80004005h
0x18001743b  mov     rcx, [rsp+158h+var_28]
0x180017443  xor     rcx, rsp; StackCookie
0x180017446  call    __security_check_cookie
0x18001744b  mov     rbx, [rsp+158h+arg_10]
0x180017453  add     rsp, 140h
0x18001745a  pop     rdi
0x18001745b  pop     rsi
0x18001745c  pop     rbp
0x18001745d  retn
```
