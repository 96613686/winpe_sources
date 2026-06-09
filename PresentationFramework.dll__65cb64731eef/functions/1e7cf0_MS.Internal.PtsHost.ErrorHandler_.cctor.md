# MS.Internal.PtsHost.ErrorHandler::.cctor

- ea: `0x1e7cf0`
- end: `0x1e7f03`
- name: `MS.Internal.PtsHost.ErrorHandler::.cctor`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x1e7cf0`: `PTS cache is already created.`
- `0x1e7cfa`: `PTS cache is already destroyed.`
- `0x1e7d0e`: `Failed to create PTS Context.`
- `0x1e7d18`: `Some enum values has been changed. Need to update dependent code.`
- `0x1e7d22`: `PTS page is not created, there is no need to destroy it.`
- `0x1e7d2c`: `Incremental update is not supported yet.`
- `0x1e7d40`: `Composite columns are not supported yet.`
- `0x1e7d72`: `Valid object is required to create handle.`
- `0x1e7d90`: `Break record already disposed.`
- `0x1e7d9a`: `There is no need to create break record.`
- `0x1e7e30`: `Container paragraph can be only created for TextElement.`
- `0x1e7e3a`: `Cannot position TextPointer inside a UIElement.`
- `0x1e7e4e`: `DocumentPage is not created for IDocumentPaginatorSource object.`
- `0x1e7e62`: `Update shifted is not a valid update type for top level PTS objects.`
- `0x1e7e94`: `Line has been already disposed.`
- `0x1e7ea8`: `Requesting data outside of line's range.`
- `0x1e7ef8`: `Paragraph's inline object cache is corrupted.`

## pseudocode

```c

```

## disassembly

```asm
0x1e7cf0  ldstr    aPtsCacheIsAlre// "PTS cache is already created."
0x1e7cf5  stsfld   string MS.Internal.PtsHost.ErrorHandler::PtsCacheAlreadyCreated
0x1e7cfa  ldstr    aPtsCacheIsAlre_0// "PTS cache is already destroyed."
0x1e7cff  stsfld   string MS.Internal.PtsHost.ErrorHandler::PtsCacheAlreadyDestroyed
0x1e7d04  ldstr    aValidPtshostOb// "Valid PtsHost object is required."
0x1e7d09  stsfld   string MS.Internal.PtsHost.ErrorHandler::NullPtsHost
0x1e7d0e  ldstr    aFailedToCreate// "Failed to create PTS Context."
0x1e7d13  stsfld   string MS.Internal.PtsHost.ErrorHandler::CreateContextFailed
0x1e7d18  ldstr    aSomeEnumValues// "Some enum values has been changed. Need"...
0x1e7d1d  stsfld   string MS.Internal.PtsHost.ErrorHandler::EnumIntegrationError
0x1e7d22  ldstr    aPtsPageIsNotCr// "PTS page is not created, there is no ne"...
0x1e7d27  stsfld   string MS.Internal.PtsHost.ErrorHandler::NoNeedToDestroyPtsPage
0x1e7d2c  ldstr    aIncrementalUpd// "Incremental update is not supported yet"...
0x1e7d31  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedFiniteIncremental
0x1e7d36  ldstr    aFootnotesAreNo// "Footnotes are not supported yet."
0x1e7d3b  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedFootnotes
0x1e7d40  ldstr    aCompositeColum// "Composite columns are not supported yet"...
0x1e7d45  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedCompositeColumns
0x1e7d4a  ldstr    aDropcapIsNotSu// "DropCap is not supported yet."
0x1e7d4f  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedDropCap
0x1e7d54  ldstr    aForcedVertical// "Forced vertical line break is not suppo"...
0x1e7d59  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedForcedLineBreaks
0x1e7d5e  ldstr    aMultiplySectio// "Multiply sections are not supported yet"...
0x1e7d63  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedMultiSection
0x1e7d68  ldstr    aColumnShifting// "Column shifting is not supported yet."
0x1e7d6d  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotSupportedSubtrackShift
0x1e7d72  ldstr    aValidObjectIsR// "Valid object is required to create hand"...
0x1e7d77  stsfld   string MS.Internal.PtsHost.ErrorHandler::NullObjectInCreateHandle
0x1e7d7c  ldstr    aNoObjectAssoci// "No object associated with the handle or"...
0x1e7d81  stsfld   string MS.Internal.PtsHost.ErrorHandler::InvalidHandle
0x1e7d86  ldstr    aObjectHandleHa// "Object handle has to be within handle a"...
0x1e7d8b  stsfld   string MS.Internal.PtsHost.ErrorHandler::HandleOutOfRange
0x1e7d90  ldstr    aBreakRecordAlr// "Break record already disposed."
0x1e7d95  stsfld   string MS.Internal.PtsHost.ErrorHandler::BreakRecordDisposed
0x1e7d9a  ldstr    aThereIsNoNeedT// "There is no need to create break record"...
0x1e7d9f  stsfld   string MS.Internal.PtsHost.ErrorHandler::BreakRecordNotNeeded
0x1e7da4  ldstr    aBrokenParagrap// "Broken paragraph cannot have margin col"...
0x1e7da9  stsfld   string MS.Internal.PtsHost.ErrorHandler::BrokenParaHasMcs
0x1e7dae  ldstr    aTopSpaceShould// "Top space should be always suppressed a"...
0x1e7db3  stsfld   string MS.Internal.PtsHost.ErrorHandler::BrokenParaHasTopSpace
0x1e7db8  ldstr    aGoalIsReachedS// "Goal is reached, so there should be no "...
0x1e7dbd  stsfld   string MS.Internal.PtsHost.ErrorHandler::GoalReachedHasBreakRecord
0x1e7dc2  ldstr    aGoalIsNotReach// "Goal is not reached, break record is re"...
0x1e7dc7  stsfld   string MS.Internal.PtsHost.ErrorHandler::BrokenContentRequiresBreakRecord
0x1e7dcc  ldstr    aPtsAssert0123// "PTS Assert:\n\t{0}\n\t{1}\n\t{2}\n\t{3}"
0x1e7dd1  stsfld   string MS.Internal.PtsHost.ErrorHandler::PTSAssert
0x1e7dd6  ldstr    aParagraphHandl// "Paragraph handle mismatch."
0x1e7ddb  stsfld   string MS.Internal.PtsHost.ErrorHandler::ParaHandleMismatch
0x1e7de0  ldstr    aActualNumberOf// "Actual number of PTS objects does not m"...
0x1e7de5  stsfld   string MS.Internal.PtsHost.ErrorHandler::PTSObjectsCountMismatch
0x1e7dea  ldstr    aSubmittingEmbe// "Submitting embedded objects for empty r"...
0x1e7def  stsfld   string MS.Internal.PtsHost.ErrorHandler::SubmitForEmptyRange
0x1e7df4  ldstr    aSubmittingInva// "Submitting invalid list of embedded obj"...
0x1e7df9  stsfld   string MS.Internal.PtsHost.ErrorHandler::SubmitInvalidList
0x1e7dfe  ldstr    aParagraphStruc// "Paragraph structure invalidation should"...
0x1e7e03  stsfld   string MS.Internal.PtsHost.ErrorHandler::HandledInsideSegmentPara
0x1e7e08  ldstr    aThereAreNoLine// "There are no lines in the paragraph."
0x1e7e0d  stsfld   string MS.Internal.PtsHost.ErrorHandler::EmptyParagraph
0x1e7e12  ldstr    aNametableIsOut// "NameTable is out of sync with TextConta"...
0x1e7e17  stsfld   string MS.Internal.PtsHost.ErrorHandler::ParaStartsWithEOP
0x1e7e1c  ldstr    aTryingToFetchP// "Trying to fetch paragraph at not suppor"...
0x1e7e21  stsfld   string MS.Internal.PtsHost.ErrorHandler::FetchParaAtTextRangePosition
0x1e7e26  ldstr    aParagraphSChar// "Paragraph's character count is out of s"...
0x1e7e2b  stsfld   string MS.Internal.PtsHost.ErrorHandler::ParagraphCharacterCountMismatch
0x1e7e30  ldstr    aContainerParag// "Container paragraph can be only created"...
0x1e7e35  stsfld   string MS.Internal.PtsHost.ErrorHandler::ContainerNeedsTextElement
0x1e7e3a  ldstr    aCannotPosition// "Cannot position TextPointer inside a UI"...
0x1e7e3f  stsfld   string MS.Internal.PtsHost.ErrorHandler::CannotPositionInsideUIElement
0x1e7e44  ldstr    aCannotFindSpec// "Cannot find specified UIElement in the "...
0x1e7e49  stsfld   string MS.Internal.PtsHost.ErrorHandler::CannotFindUIElement
0x1e7e4e  ldstr    aDocumentpageIs// "DocumentPage is not created for IDocume"...
0x1e7e53  stsfld   string MS.Internal.PtsHost.ErrorHandler::InvalidDocumentPage
0x1e7e58  ldstr    aOldParagraphDo// "Old paragraph does not have a visual no"...
0x1e7e5d  stsfld   string MS.Internal.PtsHost.ErrorHandler::NoVisualToTransfer
0x1e7e62  ldstr    aUpdateShiftedI// "Update shifted is not a valid update ty"...
0x1e7e67  stsfld   string MS.Internal.PtsHost.ErrorHandler::UpdateShiftedNotValid
0x1e7e6c  ldstr    aNumberOfColumn// "Number of column visuals does not match"...
0x1e7e71  stsfld   string MS.Internal.PtsHost.ErrorHandler::ColumnVisualCountMismatch
0x1e7e76  ldstr    aVisualDoesNotM// "Visual does not match expected type."
0x1e7e7b  stsfld   string MS.Internal.PtsHost.ErrorHandler::VisualTypeMismatch
0x1e7e80  ldstr    aEmbeddedobject// "EmbeddedObject type missmatch."
0x1e7e85  stsfld   string MS.Internal.PtsHost.ErrorHandler::EmbeddedObjectTypeMismatch
0x1e7e8a  ldstr    aCannotTransfer// "Cannot transfer data from an embedded o"...
0x1e7e8f  stsfld   string MS.Internal.PtsHost.ErrorHandler::EmbeddedObjectOwnerMismatch
0x1e7e94  ldstr    aLineHasBeenAlr// "Line has been already disposed."
0x1e7e99  stsfld   string MS.Internal.PtsHost.ErrorHandler::LineAlreadyDestroyed
0x1e7e9e  ldstr    aExpectingOnlyO// "Expecting only one rect for text object"...
0x1e7ea3  stsfld   string MS.Internal.PtsHost.ErrorHandler::OnlyOneRectIsExpected
0x1e7ea8  ldstr    aRequestingData// "Requesting data outside of line's range"...
0x1e7ead  stsfld   string MS.Internal.PtsHost.ErrorHandler::NotInLineBoundary
0x1e7eb2  ldstr    aTryingToFetchR// "Trying to fetch run at the beginning of"...
0x1e7eb7  stsfld   string MS.Internal.PtsHost.ErrorHandler::FetchRunAtTextArrayStart
0x1e7ebc  ldstr    aTextformatterH// "TextFormatter host is not initialized."
0x1e7ec1  stsfld   string MS.Internal.PtsHost.ErrorHandler::TextFormatterHostNotInitialized
0x1e7ec6  ldstr    aCharacterIndex// "Character index must be non-negative."
0x1e7ecb  stsfld   string MS.Internal.PtsHost.ErrorHandler::NegativeCharacterIndex
0x1e7ed0  ldstr    aClientdataShou// "ClientData should be always provided fo"...
0x1e7ed5  stsfld   string MS.Internal.PtsHost.ErrorHandler::NoClientDataForObjectRun
0x1e7eda  ldstr    aUnknownDepende// "Unknown DependencyObject type stored in"...
0x1e7edf  stsfld   string MS.Internal.PtsHost.ErrorHandler::UnknownDOTypeInTextArray
0x1e7ee4  ldstr    aNegativeObject// "Negative object's width within a text l"...
0x1e7ee9  stsfld   string MS.Internal.PtsHost.ErrorHandler::NegativeObjectWidth
0x1e7eee  ldstr    aTextcontainerD// "TextContainer does not have a UIElement"...
0x1e7ef3  stsfld   string MS.Internal.PtsHost.ErrorHandler::NoUIElementForObjectPosition
0x1e7ef8  ldstr    aParagraphSInli// "Paragraph's inline object cache is corr"...
0x1e7efd  stsfld   string MS.Internal.PtsHost.ErrorHandler::InlineObjectCacheCorrupted
0x1e7f02  ret
```
