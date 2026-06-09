# Streaming::StrmPostCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140001780`
- end: `0x140001864`
- name: `?StrmPostCreate@Streaming@@YA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `228`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(Streaming *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1400016fc`
- `0x140001780`
- `0x140012b18`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## string_xrefs

- `0x1400017f7`: `Streaming::StrmPostCreate() - Failed to open file with status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPostCreate(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        void *a4)
{
  struct _FILE_OBJECT *Information; // r8
  int File; // eax
  unsigned int v7; // edi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v9; // rbx
  _BYTE v11[8]; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v12; // [rsp+38h] [rbp-10h]
  const struct _FLT_RELATED_OBJECTS *v13; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v13 = a3;
    if ( ((unsigned __int8)a4 & 1) == 0 )
    {
      if ( this )
      {
        if ( a2 )
        {
          Information = (struct _FILE_OBJECT *)a2->IoStatus.Information;
          if ( Information )
          {
            File = Streaming::StrmFltInterface::CreateFile(
                     (__int64)this,
                     (struct _FLT_INSTANCE *)a2->IoStatus.Pointer,
                     Information,
                     this,
                     (__int64)&v13);
            v7 = File;
            if ( File < 0 )
            {
              this->IoStatus.Status = File;
              this->IoStatus.Information = 0;
              CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v11);
              LogWrite(
                1,
                *CurrentActivityID,
                L"Streaming::StrmPostCreate() - Failed to open file with status 0x%08X.",
                v7);
              v9 = v12;
              if ( v12 )
              {
                if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
                {
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
                  if ( !_InterlockedDecrement(v9 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
                }
              }
            }
          }
        }
      }
    }
    appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>::~auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>(
      &v13,
      a2);
  }
  return 0;
}

```

## disassembly

```asm
0x140001780  mov     r11, rsp
0x140001783  mov     [r11+8], rbx
0x140001787  push    rdi
0x140001788  sub     rsp, 40h
0x14000178c  mov     rbx, rcx
0x14000178f  test    r8, r8
0x140001792  jz      loc_140001856
0x140001798  mov     [r11+18h], r8
0x14000179c  test    r9b, 1
0x1400017a0  jnz     loc_14000184C
0x1400017a6  test    rcx, rcx
0x1400017a9  jz      loc_14000184C
0x1400017af  test    rdx, rdx
0x1400017b2  jz      loc_14000184C
0x1400017b8  mov     r8, [rdx+20h]
0x1400017bc  test    r8, r8
0x1400017bf  jz      loc_14000184C
0x1400017c5  mov     rdx, [rdx+18h]
0x1400017c9  lea     rax, [r11+18h]
0x1400017cd  mov     r9, rcx
0x1400017d0  mov     [r11-28h], rax
0x1400017d4  call    ?CreateFile@StrmFltInterface@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmCreateContext@Streaming@@U?$AllocDelete@UStrmCreateContext@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::StrmFltInterface::CreateFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>> &)
0x1400017d9  mov     edi, eax
0x1400017db  test    eax, eax
0x1400017dd  jns     short loc_14000184C
0x1400017df  lea     rcx, [rsp+48h+var_18]
0x1400017e4  mov     [rbx+18h], eax
0x1400017e7  mov     qword ptr [rbx+20h], 0
0x1400017ef  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400017f4  mov     r9d, edi
0x1400017f7  lea     r8, aStreamingStrmp; "Streaming::StrmPostCreate() - Failed to"...
0x1400017fe  mov     ecx, 1
0x140001803  mov     rdx, [rax]
0x140001806  call    LogWrite
0x14000180b  mov     rbx, [rsp+48h+var_10]
0x140001810  test    rbx, rbx
0x140001813  jz      short loc_14000184C
0x140001815  or      edi, 0FFFFFFFFh
0x140001818  mov     eax, edi
0x14000181a  lock xadd [rbx+8], eax
0x14000181f  add     eax, edi
0x140001821  jnz     short loc_14000184C
0x140001823  mov     rax, [rbx]
0x140001826  mov     rcx, rbx
0x140001829  mov     rax, [rax+8]
0x14000182d  call    _guard_dispatch_icall
0x140001832  mov     eax, edi
0x140001834  lock xadd [rbx+0Ch], eax
0x140001839  add     eax, edi
0x14000183b  jnz     short loc_14000184C
0x14000183d  mov     rax, [rbx]
0x140001840  mov     rcx, rbx
0x140001843  mov     rax, [rax+10h]
0x140001847  call    _guard_dispatch_icall
0x14000184c  lea     rcx, [rsp+48h+arg_10]
0x140001851  call    ??1?$auto_ptr@UStrmCreateContext@Streaming@@U?$AllocDelete@UStrmCreateContext@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>::~auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>(void)
0x140001856  mov     rbx, [rsp+48h+arg_0]
0x14000185b  xor     eax, eax
0x14000185d  add     rsp, 40h
0x140001861  pop     rdi
0x140001862  retn
```
