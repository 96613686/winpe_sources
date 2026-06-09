# WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 *)

- ea: `0x180020ca0`
- end: `0x180020d20`
- name: `?Decrypt@?$CEncryption@$03V?$CCipherFeistel64@$0BI@$0EI@$0EG@$0ON@$0BL@$0NO@$0DF@$0NA@$0A@$0OH@$09$0MB@$00$0M@$0HA@$0JA@$05$0MG@$0GL@$0GF@$01$0OL@$0FA@$0LK@$0L@$0JN@$0EI@$0FO@$0BG@$0NO@$0DG@$0CI@$0BC@$0KP@$0CN@$0FG@$0BK@$0HI@$0HI@$0ML@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$02$00$0CCNNJAPCKOHNKCBH@@2@UENCRYPTED_SEGMENT_DATA_CONST_5@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_5@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_5@2@@Z`
- size: `128`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011860`

## callees

- `0x180020ca0`
- `0x180022bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020cc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020cc4`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::Decrypt()
{
  return 0;
}

```

## disassembly

```asm
0x180020ca0  sub     rsp, 28h
0x180020ca4  test    dword ptr cs:qword_1800A4958, 100h
0x180020cae  jnz     short loc_180020CB8
0x180020cb0  xor     eax, eax
0x180020cb2  add     rsp, 28h
0x180020cb6  retn
0x180020cb8  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180020cbf  mov     [rsp+28h+var_8], rbx
0x180020cc4  call    cs:__imp_EnterCriticalSection
0x180020ccb  nop     dword ptr [rax+rax+00h]
0x180020cd0  mov     eax, cs:?g_EncryptedSegmentReadWriteData_60@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 WarbirdRuntime::g_EncryptedSegmentReadWriteData_60
0x180020cd6  test    eax, eax
0x180020cd8  jnz     short loc_180020CF1
0x180020cda  call    ?DoCrypt@?$CEncryption@$03V?$CCipherFeistel64@$0BI@$0EI@$0EG@$0ON@$0BL@$0NO@$0DF@$0NA@$0A@$0OH@$09$0MB@$00$0M@$0HA@$0JA@$05$0MG@$0GL@$0GF@$01$0OL@$0FA@$0LK@$0L@$0JN@$0EI@$0FO@$0BG@$0NO@$0DG@$0CI@$0BC@$0KP@$0CN@$0FG@$0BK@$0HI@$0HI@$0ML@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$02$00$0CCNNJAPCKOHNKCBH@@2@UENCRYPTED_SEGMENT_DATA_CONST_5@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_5@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_5@2@H@Z; WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 *,int)
0x180020cdf  mov     ebx, eax
0x180020ce1  test    eax, eax
0x180020ce3  js      short loc_180020D00
0x180020ce5  mov     cs:?g_EncryptedSegmentReadWriteData_60@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 WarbirdRuntime::g_EncryptedSegmentReadWriteData_60
0x180020cef  jmp     short loc_180020D00
0x180020cf1  xor     ebx, ebx
0x180020cf3  cmp     eax, 0FFFFFFFFh
0x180020cf6  jz      short loc_180020D00
0x180020cf8  inc     eax
0x180020cfa  mov     cs:?g_EncryptedSegmentReadWriteData_60@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5 WarbirdRuntime::g_EncryptedSegmentReadWriteData_60
0x180020d00  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180020d07  call    cs:__imp_LeaveCriticalSection
0x180020d0e  nop     dword ptr [rax+rax+00h]
0x180020d13  mov     eax, ebx
0x180020d15  mov     rbx, [rsp+28h+var_8]
0x180020d1a  add     rsp, 28h
0x180020d1e  retn
```
