# ClientPicker::Initialize(DirectUI::Element *,ulong *)

- ea: `0x18000b8ac`
- end: `0x18000b9c7`
- name: `?Initialize@ClientPicker@@QEAAJPEAVElement@DirectUI@@PEAK@Z`
- size: `283`
- prototype: `__int64 __fastcall(ClientPicker *__hidden this, struct DirectUI::Element *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a720`

## callees

- `0x18000a360`
- `0x18000b8ac`

## import_xrefs

- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000b8c6`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x18000b8c6`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b9a0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b9af`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b9a0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b9af`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b928`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b96c`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b928`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000b96c`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000b8fa`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18000b8fa`
- `DUI70!?Create@Combobox@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x18000b95c`
- `DUI70!?Create@Combobox@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x18000b95c`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18000b947`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18000b947`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b939`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b939`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000b912`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000b912`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18000b991`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18000b991`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b97d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000b97d`

## pseudocode

```c
int __fastcall ClientPicker::Initialize(
        struct DirectUI::Element **this,
        struct DirectUI::Element *a2,
        unsigned int *a3)
{
  int result; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  DirectUI::Element **v7; // rdi
  int v8; // esi
  struct DirectUI::Element **v9; // rsi
  int v10; // edi

  result = DirectUI::Element::Initialize((DirectUI::Element *)this, 0, a2, a3);
  if ( result >= 0 )
  {
    result = DirectUI::DynamicArray<CLIENTINFO *,0>::Create(v6, v5, this + 28);
    if ( result >= 0 )
    {
      v7 = this + 29;
      result = DirectUI::Element::Create(0, (struct DirectUI::Element *)this, 0, this + 29);
      if ( result >= 0 )
      {
        v8 = DirectUI::Element::SetClass(*v7, L"clientstatic");
        if ( v8 < 0 || (v8 = DirectUI::Element::Add((DirectUI::Element *)this, *v7), v8 < 0) )
        {
          DirectUI::Element::Destroy(*v7, 1);
          return v8;
        }
        else
        {
          DirectUI::Element::SetAccessible(*v7, 1);
          DirectUI::Element::SetAccRole(*v7, 41);
          v9 = this + 30;
          result = DirectUI::Combobox::Create((struct DirectUI::Element *)this, 0, this + 30);
          if ( result >= 0 )
          {
            v10 = DirectUI::Element::Add((DirectUI::Element *)this, *v9);
            if ( v10 < 0 || (v10 = DirectUI::Element::SetVisible(*v9, 0), v10 < 0) )
            {
              DirectUI::Element::Destroy(*v9, 1);
              return v10;
            }
            else
            {
              DirectUI::Element::SetWidth((DirectUI::Element *)this, 10);
              return 0;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b8ac  mov     [rsp+arg_0], rbx
0x18000b8b1  mov     [rsp+arg_8], rsi
0x18000b8b6  push    rdi
0x18000b8b7  sub     rsp, 20h
0x18000b8bb  mov     r9, r8
0x18000b8be  mov     rbx, rcx
0x18000b8c1  mov     r8, rdx
0x18000b8c4  xor     edx, edx
0x18000b8c6  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x18000b8cc  test    eax, eax
0x18000b8ce  js      loc_18000B9B7
0x18000b8d4  lea     r8, [rbx+0E0h]
0x18000b8db  call    ?Create@?$DynamicArray@PEAVCLIENTINFO@@$0A@@DirectUI@@SAJI_NPEAPEAV12@@Z; DirectUI::DynamicArray<CLIENTINFO *,0>::Create(uint,bool,DirectUI::DynamicArray<CLIENTINFO *,0> * *)
0x18000b8e0  test    eax, eax
0x18000b8e2  js      loc_18000B9B7
0x18000b8e8  lea     rdi, [rbx+0E8h]
0x18000b8ef  xor     r8d, r8d
0x18000b8f2  mov     r9, rdi
0x18000b8f5  mov     rdx, rbx
0x18000b8f8  xor     ecx, ecx
0x18000b8fa  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000b900  test    eax, eax
0x18000b902  js      loc_18000B9B7
0x18000b908  mov     rcx, [rdi]
0x18000b90b  lea     rdx, aClientstatic; "clientstatic"
0x18000b912  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18000b918  mov     esi, eax
0x18000b91a  test    eax, eax
0x18000b91c  js      loc_18000B9AA
0x18000b922  mov     rdx, [rdi]
0x18000b925  mov     rcx, rbx
0x18000b928  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000b92e  mov     esi, eax
0x18000b930  test    eax, eax
0x18000b932  js      short loc_18000B9AA
0x18000b934  mov     rcx, [rdi]
0x18000b937  mov     dl, 1
0x18000b939  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18000b93f  mov     rcx, [rdi]
0x18000b942  mov     edx, 29h ; ')'
0x18000b947  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18000b94d  lea     rsi, [rbx+0F0h]
0x18000b954  xor     edx, edx
0x18000b956  mov     r8, rsi
0x18000b959  mov     rcx, rbx
0x18000b95c  call    cs:__imp_?Create@Combobox@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z; DirectUI::Combobox::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000b962  test    eax, eax
0x18000b964  js      short loc_18000B9B7
0x18000b966  mov     rdx, [rsi]
0x18000b969  mov     rcx, rbx
0x18000b96c  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000b972  mov     edi, eax
0x18000b974  test    eax, eax
0x18000b976  js      short loc_18000B99B
0x18000b978  mov     rcx, [rsi]
0x18000b97b  xor     edx, edx
0x18000b97d  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000b983  mov     edi, eax
0x18000b985  test    eax, eax
0x18000b987  js      short loc_18000B99B
0x18000b989  mov     edx, 0Ah
0x18000b98e  mov     rcx, rbx
0x18000b991  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18000b997  xor     eax, eax
0x18000b999  jmp     short loc_18000B9B7
0x18000b99b  mov     rcx, [rsi]
0x18000b99e  mov     dl, 1
0x18000b9a0  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000b9a6  mov     eax, edi
0x18000b9a8  jmp     short loc_18000B9B7
0x18000b9aa  mov     rcx, [rdi]
0x18000b9ad  mov     dl, 1
0x18000b9af  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000b9b5  mov     eax, esi
0x18000b9b7  mov     rbx, [rsp+28h+arg_0]
0x18000b9bc  mov     rsi, [rsp+28h+arg_8]
0x18000b9c1  add     rsp, 20h
0x18000b9c5  pop     rdi
0x18000b9c6  retn
```
