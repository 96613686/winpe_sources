# bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &)

- ea: `0x1800231d0`
- end: `0x1800232ff`
- name: `??$DoublePassApply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@detail@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@1@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@Z`
- size: `303`
- prototype: `char __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180023850`

## callees

- `0x18001fa54`
- `0x180023444`
- `0x180023588`
- `0x180023850`
- `0x180023c4c`
- `0x18002a030`

## pseudocode

```c
char __fastcall bond::detail::DoublePassApply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  unsigned int v6; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-D8h] BYREF
  char v8; // [rsp+30h] [rbp-D0h]
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v10; // [rsp+50h] [rbp-B0h]
  _DWORD v11[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v12; // [rsp+60h] [rbp-A0h] BYREF
  char *v13; // [rsp+160h] [rbp+60h]
  _DWORD v14[2]; // [rsp+168h] [rbp+68h] BYREF
  char v15; // [rsp+170h] [rbp+70h] BYREF
  char *v16; // [rsp+270h] [rbp+170h]

  v3 = a1;
  v6 = 0;
  v9[0] = &v6;
  v10 = *(_WORD *)(*a1 + 16LL);
  v11[0] = 0;
  v11[1] = 64;
  v13 = &v12;
  v14[0] = 0;
  v14[1] = 64;
  v16 = &v15;
  v7 = v9;
  v8 = 0;
  bond::detail::SimpleArray<unsigned int,64>::push(v11, 0);
  bond::detail::SimpleArray<unsigned int,64>::push(v14, v6);
  bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<unsigned __int64>(
    &v7,
    0,
    Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata,
    a2);
  ++*(_DWORD *)v9[0];
  bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(v9, v9[0]);
  v4 = (_QWORD *)*v3;
  v4[1] = v16;
  v7 = v4;
  LOBYTE(v3) = bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(
                 (__int64)v3,
                 a2);
  v4[1] = 0;
  bond::detail::SimpleArray<unsigned int,64>::memfree(v14);
  bond::detail::SimpleArray<unsigned int,64>::memfree(v11);
  return (char)v3;
}

```

## disassembly

```asm
0x1800231d0  mov     [rsp-8+arg_10], rbx
0x1800231d5  push    rbp
0x1800231d6  push    rsi
0x1800231d7  push    rdi
0x1800231d8  lea     rbp, [rsp-190h]
0x1800231e0  sub     rsp, 290h
0x1800231e7  mov     rax, cs:__security_cookie
0x1800231ee  xor     rax, rsp
0x1800231f1  mov     [rbp+1A0h+var_20], rax
0x1800231f8  mov     rsi, rdx
0x1800231fb  mov     rbx, rcx
0x1800231fe  mov     [rsp+2A0h+var_280], 0
0x180023206  lea     rax, [rsp+2A0h+var_280]
0x18002320b  mov     [rsp+2A0h+var_260], rax
0x180023210  mov     rax, [rcx]
0x180023213  movzx   ecx, word ptr [rax+10h]
0x180023217  mov     [rsp+2A0h+var_250], cx
0x18002321c  mov     [rsp+2A0h+var_248], 0
0x180023224  mov     ecx, 40h ; '@'
0x180023229  mov     [rsp+2A0h+var_244], ecx
0x18002322d  lea     rax, [rsp+2A0h+var_240]
0x180023232  mov     [rbp+1A0h+var_140], rax
0x180023236  mov     [rbp+1A0h+var_138], 0
0x18002323d  mov     [rbp+1A0h+var_134], ecx
0x180023240  lea     rax, [rbp+1A0h+var_130]
0x180023244  mov     [rbp+1A0h+var_30], rax
0x18002324b  lea     rax, [rsp+2A0h+var_260]
0x180023250  mov     [rsp+2A0h+var_278], rax
0x180023255  mov     [rsp+2A0h+var_270], 0
0x18002325a  xor     edx, edx
0x18002325c  lea     rcx, [rsp+2A0h+var_248]
0x180023261  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x180023266  mov     edx, [rsp+2A0h+var_280]
0x18002326a  lea     rcx, [rbp+1A0h+var_138]
0x18002326e  call    ?push@?$SimpleArray@I$0EA@@detail@bond@@QEAAXI@Z; bond::detail::SimpleArray<uint,64>::push(uint)
0x180023273  xor     edx, edx
0x180023275  mov     r9, rsi
0x180023278  lea     r8, ?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B; bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata
0x18002327f  lea     rcx, [rsp+2A0h+var_278]
0x180023284  call    ??$Field@_K@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_K@Z; bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<unsigned __int64>(ushort,bond::Metadata const &,unsigned __int64 const &)
0x180023289  mov     r11, [rsp+2A0h+var_260]
0x18002328e  inc     dword ptr [r11]
0x180023291  mov     rdx, [rsp+2A0h+var_260]
0x180023296  lea     rcx, [rsp+2A0h+var_260]
0x18002329b  call    ?LengthEnd@?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@IEAAXAEAVOutputCounter@2@@Z; bond::CompactBinaryWriter<bond::OutputCounter>::LengthEnd(bond::OutputCounter &)
0x1800232a0  mov     rdi, [rbx]
0x1800232a3  mov     rax, [rbp+1A0h+var_30]
0x1800232aa  mov     [rdi+8], rax
0x1800232ae  mov     [rsp+2A0h+var_278], rdi
0x1800232b3  mov     rdx, rsi
0x1800232b6  mov     rcx, rbx
0x1800232b9  call    ??$Apply@V?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@YA_NAEBV?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@0@AEBV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@Z; bond::Apply<bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>(bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>> const &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature> const &)
0x1800232be  mov     bl, al
0x1800232c0  mov     qword ptr [rdi+8], 0
0x1800232c8  lea     rcx, [rbp+1A0h+var_138]
0x1800232cc  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x1800232d1  lea     rcx, [rsp+2A0h+var_248]
0x1800232d6  call    ?memfree@?$SimpleArray@I$0EA@@detail@bond@@AEAAXXZ; bond::detail::SimpleArray<uint,64>::memfree(void)
0x1800232db  mov     al, bl
0x1800232dd  mov     rcx, [rbp+1A0h+var_20]
0x1800232e4  xor     rcx, rsp; StackCookie
0x1800232e7  call    __security_check_cookie
0x1800232ec  mov     rbx, [rsp+2A0h+arg_10]
0x1800232f4  add     rsp, 290h
0x1800232fb  pop     rdi
0x1800232fc  pop     rsi
0x1800232fd  pop     rbp
0x1800232fe  retn
```
