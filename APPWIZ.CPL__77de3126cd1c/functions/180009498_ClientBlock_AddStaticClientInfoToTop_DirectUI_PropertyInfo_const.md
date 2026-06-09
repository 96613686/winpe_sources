# ClientBlock::AddStaticClientInfoToTop(DirectUI::PropertyInfo const *)

- ea: `0x180009498`
- end: `0x180009549`
- name: `?AddStaticClientInfoToTop@ClientBlock@@QEAAJPEBUPropertyInfo@DirectUI@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(ClientBlock *__hidden this, const struct DirectUI::PropertyInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cec4`

## callees

- `0x18000625c`
- `0x180008ddc`
- `0x180009498`
- `0x18000a460`
- `0x18000bc98`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800094b1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000950b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800094b1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000950b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800094d8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800094d8`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800094bd`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180009518`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800094bd`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180009518`

## pseudocode

```c
__int64 __fastcall ClientBlock::AddStaticClientInfoToTop(ClientBlock *this, const struct DirectUI::PropertyInfo *a2)
{
  DirectUI::Value *Value; // rbx
  const WCHAR *String; // rax
  struct CLIENTINFO *v5; // rdi
  int v6; // ebx
  DirectUI::Value *v7; // rax
  void *v8; // rdx

  Value = DirectUI::Element::GetValue(this, a2, 2, 0);
  String = DirectUI::Value::GetString(Value);
  v5 = CLIENTINFO::Create(0, 0, String, 0);
  DirectUI::Value::Release(Value);
  if ( v5 )
  {
    v6 = DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(
           *((_QWORD *)this + 25),
           0,
           v5);
    if ( v6 < 0 )
    {
      CLIENTINFO::~CLIENTINFO(v5);
      DirectUI::HFree(v5, v8);
    }
    else
    {
      v7 = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_180077428, 2, 0);
      *((_QWORD *)v5 + 3) = v7;
      DirectUI::Value::GetString(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009498  mov     [rsp+arg_0], rbx
0x18000949d  mov     [rsp+arg_8], rsi
0x1800094a2  push    rdi
0x1800094a3  sub     rsp, 20h
0x1800094a7  xor     r9d, r9d
0x1800094aa  mov     rsi, rcx
0x1800094ad  lea     r8d, [r9+2]
0x1800094b1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800094b7  mov     rcx, rax
0x1800094ba  mov     rbx, rax
0x1800094bd  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800094c3  xor     r9d, r9d; bool
0x1800094c6  xor     edx, edx; HKEY
0x1800094c8  mov     r8, rax; pszSrch
0x1800094cb  xor     ecx, ecx; hkey
0x1800094cd  call    ?Create@CLIENTINFO@@SAPEAV1@PEAUHKEY__@@0PEBG_N@Z; CLIENTINFO::Create(HKEY__ *,HKEY__ *,ushort const *,bool)
0x1800094d2  mov     rcx, rbx
0x1800094d5  mov     rdi, rax
0x1800094d8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800094de  test    rdi, rdi
0x1800094e1  jz      short loc_180009532
0x1800094e3  mov     rcx, [rsi+0C8h]
0x1800094ea  mov     r8, rdi
0x1800094ed  xor     edx, edx
0x1800094ef  call    ?Insert@?$DynamicArrayBase@PEAVCLIENTINFO@@V?$DoubleAllocationPolicy@PEAVCLIENTINFO@@@DirectUI@@$00$0A@@DirectUI@@QEAAJIPEAVCLIENTINFO@@@Z; DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(uint,CLIENTINFO *)
0x1800094f4  mov     ebx, eax
0x1800094f6  test    eax, eax
0x1800094f8  js      short loc_180009520
0x1800094fa  xor     r9d, r9d
0x1800094fd  lea     rdx, off_180077428; "KeepMSText"
0x180009504  mov     rcx, rsi
0x180009507  lea     r8d, [r9+2]
0x18000950b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180009511  mov     rcx, rax
0x180009514  mov     [rdi+18h], rax
0x180009518  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000951e  jmp     short loc_180009537
0x180009520  mov     rcx, rdi; this
0x180009523  call    ??1CLIENTINFO@@QEAA@XZ; CLIENTINFO::~CLIENTINFO(void)
0x180009528  mov     rcx, rdi; this
0x18000952b  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x180009530  jmp     short loc_180009537
0x180009532  mov     ebx, 8007000Eh
0x180009537  mov     rsi, [rsp+28h+arg_8]
0x18000953c  mov     eax, ebx
0x18000953e  mov     rbx, [rsp+28h+arg_0]
0x180009543  add     rsp, 20h
0x180009547  pop     rdi
0x180009548  retn
```
