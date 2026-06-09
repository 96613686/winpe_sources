# Streaming::StrmPostQueryInfoWorker(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x1400018d0`
- end: `0x140001971`
- name: `?StrmPostQueryInfoWorker@Streaming@@YA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `161`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400018d0`
- `0x14000bcb0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14000195c`
- `FLTMGR!FltReleaseContext` at `0x14000195c`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPostQueryInfoWorker(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  struct _FILE_OBJECT *FileObject; // rdx
  struct _FLT_INSTANCE *Instance; // rcx
  NTSTATUS Status; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG Options; // ecx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  if ( Data )
  {
    if ( FltObjects )
    {
      FileObject = FltObjects->FileObject;
      if ( FileObject )
      {
        Instance = FltObjects->Instance;
        Context = 0;
        if ( (int)Streaming::Context::StreamContextFactory::GetStreamContext(Instance, FileObject, &Context) >= 0 )
        {
          Status = Data->IoStatus.Status;
          if ( !Status || Status == -2147483643 )
          {
            Iopb = Data->Iopb;
            Options = Iopb->Parameters.Create.Options;
            if ( (Options == 4 || Options == 18) && Iopb->Parameters.Read.Length >= 0x28 )
            {
              *(_DWORD *)(Iopb->Parameters.Read.ByteOffset.QuadPart + 32) &= ~0x400u;
            }
            else if ( Options == 34 && Iopb->Parameters.Read.Length >= 0x38 )
            {
              *(_DWORD *)(Iopb->Parameters.Read.ByteOffset.QuadPart + 48) &= ~0x400u;
            }
          }
        }
        if ( Context )
          FltReleaseContext(Context);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400018d0  push    rbx
0x1400018d2  sub     rsp, 20h
0x1400018d6  mov     rax, rdx
0x1400018d9  mov     rbx, rcx
0x1400018dc  test    rcx, rcx
0x1400018df  jz      loc_140001968
0x1400018e5  test    rax, rax
0x1400018e8  jz      short loc_140001968
0x1400018ea  mov     rdx, [rdx+20h]
0x1400018ee  test    rdx, rdx
0x1400018f1  jz      short loc_140001968
0x1400018f3  mov     rcx, [rax+18h]
0x1400018f7  lea     r8, [rsp+28h+Context]
0x1400018fc  mov     [rsp+28h+Context], 0
0x140001905  call    ?GetStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetStreamContext(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x14000190a  test    eax, eax
0x14000190c  js      short loc_140001952
0x14000190e  mov     eax, [rbx+18h]
0x140001911  test    eax, eax
0x140001913  jz      short loc_14000191C
0x140001915  cmp     eax, 80000005h
0x14000191a  jnz     short loc_140001952
0x14000191c  mov     rax, [rbx+10h]
0x140001920  mov     ecx, [rax+20h]
0x140001923  cmp     ecx, 4
0x140001926  jz      short loc_14000192D
0x140001928  cmp     ecx, 12h
0x14000192b  jnz     short loc_14000193E
0x14000192d  cmp     dword ptr [rax+18h], 28h ; '('
0x140001931  jb      short loc_14000193E
0x140001933  mov     rax, [rax+28h]
0x140001937  btr     dword ptr [rax+20h], 0Ah
0x14000193c  jmp     short loc_140001952
0x14000193e  cmp     ecx, 22h ; '"'
0x140001941  jnz     short loc_140001952
0x140001943  cmp     dword ptr [rax+18h], 38h ; '8'
0x140001947  jb      short loc_140001952
0x140001949  mov     rax, [rax+28h]
0x14000194d  btr     dword ptr [rax+30h], 0Ah
0x140001952  mov     rcx, [rsp+28h+Context]; Context
0x140001957  test    rcx, rcx
0x14000195a  jz      short loc_140001968
0x14000195c  call    cs:__imp_FltReleaseContext
0x140001963  nop     dword ptr [rax+rax+00h]
0x140001968  xor     eax, eax
0x14000196a  add     rsp, 20h
0x14000196e  pop     rbx
0x14000196f  retn
```
