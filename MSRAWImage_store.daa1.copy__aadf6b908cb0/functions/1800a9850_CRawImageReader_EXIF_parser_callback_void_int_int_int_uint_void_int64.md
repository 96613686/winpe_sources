# CRawImageReader::EXIF_parser_callback(void *,int,int,int,uint,void *,__int64)

- ea: `0x1800a9850`
- end: `0x1800a98b9`
- name: `?EXIF_parser_callback@CRawImageReader@@SAXPEAXHHHI0_J@Z`
- size: `105`
- prototype: `void __usercall(CRawImageReader *this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, unsigned int, void *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001a40`
- `0x180096d4c`
- `0x1800a9850`
- `0x1800ad270`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRawImageReader::EXIF_parser_callback(
        CRawImageReader *this,
        volatile int *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        void *a6)
{
  int v6; // edi
  unsigned int v8; // r10d
  unsigned __int16 v9; // r11
  volatile int *v10; // rdx

  if ( this )
  {
    v6 = (int)a2;
    Microsoft::WRL::Details::SafeUnknownIncrementReference((CRawImageReader *)((char *)this + 52), a2);
    CRawImageReader::CopyEXIFData(this, v6, v9, v8, a5, a6);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(
      (__int64)this,
      v10);
  }
}

```

## disassembly

```asm
0x1800a9850  test    rcx, rcx
0x1800a9853  jz      short locret_1800A98B7
0x1800a9855  push    rdi
0x1800a9856  sub     rsp, 40h
0x1800a985a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a9863  mov     [rsp+48h+arg_8], rbx
0x1800a9868  mov     r10d, r9d
0x1800a986b  mov     r11d, r8d
0x1800a986e  mov     edi, edx
0x1800a9870  mov     rbx, rcx
0x1800a9873  mov     [rsp+48h+arg_0], rcx
0x1800a9878  add     rcx, 34h ; '4'; this
0x1800a987c  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800a9881  nop
0x1800a9882  mov     rax, [rsp+48h+arg_28]
0x1800a9887  mov     [rsp+48h+var_20], rax; void *
0x1800a988c  mov     eax, [rsp+48h+arg_20]
0x1800a9890  mov     [rsp+48h+var_28], eax; unsigned int
0x1800a9894  mov     r9d, r10d; int
0x1800a9897  mov     r8d, r11d; int
0x1800a989a  mov     edx, edi; int
0x1800a989c  mov     rcx, rbx; this
0x1800a989f  call    ?CopyEXIFData@CRawImageReader@@AEAAXHHHIPEAX@Z; CRawImageReader::CopyEXIFData(int,int,int,uint,void *)
0x1800a98a4  nop
0x1800a98a5  mov     rcx, rbx
0x1800a98a8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(void)
0x1800a98ad  mov     rbx, [rsp+48h+arg_8]
0x1800a98b2  add     rsp, 40h
0x1800a98b6  pop     rdi
0x1800a98b7  retn
```
